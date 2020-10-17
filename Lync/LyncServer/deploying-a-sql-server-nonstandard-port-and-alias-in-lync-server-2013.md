---
title: Lync Server 2013 での SQL Server の標準以外のポートとエイリアスの展開
description: Lync Server 2013 で SQL Server の標準以外のポートとエイリアスを展開します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a SQL Server nonstandard port and alias in Lync Server 2013
ms:assetid: 2da92c1f-250e-407a-8651-fb2aec76aeb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn776290(v=OCS.15)
ms:contentKeyID: 62634609
ms.date: 09/17/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da76db2b946a47e13fe3549d7184b0b12894a83a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551233"
---
# <a name="deploying-a-sql-server-nonstandard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="63626-103">Lync Server 2013 での SQL Server の標準以外のポートとエイリアスの展開</span><span class="sxs-lookup"><span data-stu-id="63626-103">Deploying a SQL Server nonstandard port and alias in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63626-104">_**トピックの最終更新日:** 2015-09-16_</span><span class="sxs-lookup"><span data-stu-id="63626-104">_**Topic Last Modified:** 2015-09-16_</span></span>

<span data-ttu-id="63626-105">Microsoft Lync Server 2013 は、SQL Server で標準以外のポートとエイリアスを使用することをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="63626-105">Microsoft Lync Server 2013 supports using a non-standard port and alias in SQL Server.</span></span> <span data-ttu-id="63626-106">SQL Server の非標準ポートとエイリアスを使用すると、セキュリティが向上し、Lync 展開により柔軟な環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="63626-106">Using a SQL Server non-standard port and an alias increases security and creates a more flexible environment for the Lync deployment.</span></span> <span data-ttu-id="63626-107">これらの手順は、Lync Server 2013 環境を適切にセキュリティで保護する手順の1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="63626-107">These steps are only a single step in properly securing your Lync Server 2013 environment.</span></span> <span data-ttu-id="63626-108">Lync Server 2013 実装の攻撃対象を減らすには、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-108">Additional steps should be taken to reduce the attack surface of a Lync Server 2013 implementation.</span></span>

<span data-ttu-id="63626-109">次の記事では、Lync Server 2013 で標準以外の SQL Server のポートとエイリアスをセットアップするために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="63626-109">The following article describes the steps required to setup a SQL Server non-standard port and alias in Lync Server 2013.</span></span>

<div>

## <a name="deploying-a-sql-server-non-standard-port-and-alias-in-lync-server-2013"></a><span data-ttu-id="63626-110">Lync Server 2013 に SQL Server の非標準ポートとエイリアスを展開する</span><span class="sxs-lookup"><span data-stu-id="63626-110">Deploying a SQL Server Non-Standard Port and Alias in Lync Server 2013</span></span>

<span data-ttu-id="63626-111">Lync Server 2013 トポロジビルダーでは、Lync Server 2013 を構成する際に、実際の SQL Server の FQDN ではなく、完全修飾ドメイン名 (FQDN) として SQL Server のエイリアスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="63626-111">Lync Server 2013 Topology Builder supports using a SQL Server alias as the Fully Qualified Domain Name (FQDN) instead of the actual SQL Server FQDN when configuring Lync Server 2013.</span></span> <span data-ttu-id="63626-112">これにより、実際の SQL Server の FQDN を悪意のある攻撃者に対して非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="63626-112">This allows the actual SQL Server FQDN to be hidden from any malicious attacker.</span></span> <span data-ttu-id="63626-113">また、次の図に示されているように、標準ポート1433上のデータベースを攻撃しようとしている場合に、非標準ポートを使用して、次の図に示すように、実際のポートを不明瞭にします。</span><span class="sxs-lookup"><span data-stu-id="63626-113">In addition, using a non-standard port obscures the actual port from any would be attacker attempting to attack the database on the standard port 1433, as shown in the following figure.</span></span>

<span data-ttu-id="63626-114">![ハッカーは、攻撃対象のポート番号を認識していません。](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "ハッカーは、攻撃対象のポート番号を認識していません。")</span><span class="sxs-lookup"><span data-stu-id="63626-114">![A hacker doesn't know the port number to attack.](images/Dn776290.2f3923e0-2bdc-416b-a66b-bf56599eb14e(OCS.15).jpg "A hacker doesn't know the port number to attack.")</span></span>

<span data-ttu-id="63626-115">SQL Server との通信に使用している Lync Server 2013 のポートを正しく判断するには、攻撃者はすべてのポートをスキャンしてポート情報を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-115">In order to be successful in determining the port Lync Server 2013 is using to communicate with SQL Server, the attacker would need to scan all ports to obtain the port information.</span></span> <span data-ttu-id="63626-116">攻撃者によるポートスキャンでは、セキュリティが命令を検出して停止する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="63626-116">A port scan by an attacker increases the chances that security can detect and stop the instruction.</span></span> <span data-ttu-id="63626-117">拡張セキュリティを標準以外のポートで追加することに加えて、SQL Server の別名を使用して展開の柔軟性を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="63626-117">In addition to adding increased security with a non-standard port, you can also use a SQL Server alias to provide flexibility for the deployment.</span></span> <span data-ttu-id="63626-118">これは、SQL Server の名前の変更が必要になる状況での構成変更を減らすために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="63626-118">This is valuable in order to reduce configuration changes in situations where a SQL Server name change is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63626-119">SQL Server には、2つのフォールトトレランス方法 (フェールオーバークラスタリングとミラーリング) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="63626-119">SQL Server provides two fault tolerance methods (Failover Clustering and Mirroring).</span></span> <span data-ttu-id="63626-120">Sql Server のフォールトトレランス方式は、SQL Server の非標準ポートと、Lync Server 2013 でエイリアスを使用してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="63626-120">Both SQL Server fault tolerance methods are supported using a SQL Server non-standard port and alias with Lync Server 2013.</span></span> <span data-ttu-id="63626-121">プールによって使用される SQL Server バックエンドがミラーリングされた構成にある場合は、データベースがミラーリングされた SQL Server にフェールオーバーするときに、SQL Server バックエンドサーバー上の SQL browser サービスが、ミラーリングされたデータベースに接続するために実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-121">If the SQL Server backend used by the pool is in a mirrored configuration, then the SQL browser service on the SQL Server backend servers should be running for Front End servers to connect to the mirrored database when the databases are failed over to the mirrored SQL Server.</span></span>



</div>

<span data-ttu-id="63626-122">トポロジビルダー内から SQL Server データベース接続を構成する場合、または Install-CsDatabase コマンドレットを使用する場合は、SQL Server の非標準ポート番号を明示的に定義して SQL インスタンスに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="63626-122">When configuring SQL Server database connectivity from within Topology Builder, or when using the Install-CsDatabase cmdlet, it’s not possible to explicitly define a SQL Server non-standard port number and associate it with a SQL instance.</span></span> <span data-ttu-id="63626-123">非標準ポートを設定するには、SQL Server および Windows Server ユーティリティを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-123">To set a non-standard port, you’ll need to use SQL Server and Windows Server utilities.</span></span>

<span data-ttu-id="63626-124">Lync Server 2013 で使用するために SQL Server の非標準ポートとエイリアスをセットアップするには、3つの主要な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-124">To set up a SQL Server non-standard port and alias for use with Lync Server 2013, you will need to complete three primary steps.</span></span> <span data-ttu-id="63626-125">その手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63626-125">These steps are:</span></span>

  - <span data-ttu-id="63626-126">Lync Server 2013 に最新の更新プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63626-126">Confirm that Lync Server 2013 has the Latest Updates Applied.</span></span>

  - <span data-ttu-id="63626-127">SQL Server の非標準ポートとエイリアスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="63626-127">Setup the SQL Server Non-Standard Port and Alias.</span></span>

  - <span data-ttu-id="63626-128">トポロジビルダーを使用して、SQL Server エイリアスを使用して Lync Server 2013 を構成します。</span><span class="sxs-lookup"><span data-stu-id="63626-128">Configure Lync Server 2013 with the SQL Server alias using Topology Builder.</span></span>

  - <span data-ttu-id="63626-129">トポロジを公開し、データベースを確認します。</span><span class="sxs-lookup"><span data-stu-id="63626-129">Publish the Topology, and Verify the Database.</span></span>

<div>

## <a name="confirm-that-lync-server-2013-has-the-latest-updates-applied"></a><span data-ttu-id="63626-130">Lync Server 2013 に最新の更新プログラムが適用されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="63626-130">Confirm that Lync Server 2013 has the Latest Updates Applied</span></span>

<span data-ttu-id="63626-131">Lync Server 2013 を最新の状態に保つことが重要です。</span><span class="sxs-lookup"><span data-stu-id="63626-131">It is important to keep Lync Server 2013 up to date.</span></span> <span data-ttu-id="63626-132">最新の更新プログラムとその適用方法に関する情報を確認するには、「 [Lync Server 2013 の更新プログラム](https://support.microsoft.com/kb/2809243)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63626-132">To check for the most recent updates and information on how to apply them, see [Updates for Lync Server 2013](https://support.microsoft.com/kb/2809243).</span></span>

</div>

<div>

## <a name="setup-the-sql-server-non-standard-port-and-alias"></a><span data-ttu-id="63626-133">SQL Server の非標準ポートとエイリアスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="63626-133">Setup the SQL Server Non-Standard Port and Alias</span></span>

<span data-ttu-id="63626-134">Lync Server 2013 トポロジビルダーから参照できるようにするには、SQL Server の非標準ポートとエイリアスをデータベースインスタンスで設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-134">The SQL Server non-standard port and alias must be set up on the database instance before it can be referenced from Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="63626-135">SQL Server の非標準ポートとエイリアスをセットアップするには、3つの主要な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-135">To set up a SQL Server non-standard port and alias, you will have to complete three primary steps.</span></span> <span data-ttu-id="63626-136">これらの手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63626-136">These steps are as follows:</span></span>

  - <span data-ttu-id="63626-137">既定の TCP/IP プロトコルの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="63626-137">Change the Default TCP/IP Protocol Values.</span></span>

  - <span data-ttu-id="63626-138">SQL Server エイリアスを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="63626-138">Create and Configure a SQL Server Alias.</span></span>

  - <span data-ttu-id="63626-139">ドメインネームシステム (DNS) 正規名 (CNAME) リソースレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="63626-139">Create a Domain Name System (DNS) Canonical Name (CNAME) Resource Record.</span></span>

<span data-ttu-id="63626-140">**既定の TCP/IP プロトコル値を変更する**</span><span class="sxs-lookup"><span data-stu-id="63626-140">**Modify the Default TCP/IP Protocol Values**</span></span>

1.  <span data-ttu-id="63626-141">次の図に示すように、[ **スタート**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-141">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-142">![SQL Server Management Studio アイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio アイコン")</span><span class="sxs-lookup"><span data-stu-id="63626-142">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="63626-143">次の図に示すように、ナビゲーションウィンドウで、 **Sql server インスタンス**を選択し、[ **Sql server ネットワーク構成**] を展開して、[\*\*プロトコル \<instance name\> \*\*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-143">In the navigation pane, choose to expand the **SQL Server instance**, choose to expand **SQL Server Network Configuration**, and choose **Protocols for \<instance name\>**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-144">![[TCP/IP のプロパティ] に移動します。](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "[TCP/IP のプロパティ] に移動します。")</span><span class="sxs-lookup"><span data-stu-id="63626-144">![Navigate to TCP/IP Properties](images/Dn776290.3d7a964c-f17e-47fd-8f0c-535453da7fad(OCS.15).jpg "Navigate to TCP/IP Properties")</span></span>

3.  <span data-ttu-id="63626-145">右側のウィンドウで、[ **tcp/ip**] を右クリックし、[ **プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-145">In the right pane, right-click **TCP/IP**, and select **Properties**.</span></span> <span data-ttu-id="63626-146">[TCP/IP のプロパティ] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63626-146">The TCP/IP Properties dialog box is displayed.</span></span>

4.  <span data-ttu-id="63626-147">[ **IP アドレス** ] タブを選択します。[IP アドレス] タブには、サーバー上のすべてのアクティブな IP アドレスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63626-147">Select the **IP Addresses** tab. The IP Addresses tab shows all of the active IP addresses on the server.</span></span> <span data-ttu-id="63626-148">次の図に示すように、これらは IP1, IP2 の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="63626-148">These are in the format IP1, IP2, up to IPAll, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-149">![TCP/IP のプロパティを開きます。](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "TCP/IP のプロパティを開きます。")</span><span class="sxs-lookup"><span data-stu-id="63626-149">![Open TCP/IP properties.](images/Dn776290.ed2fd70d-1836-4ebf-80fe-09191d96585e(OCS.15).jpg "Open TCP/IP properties.")</span></span>

5.  <span data-ttu-id="63626-150">すべての IP アドレスの [ **TCP 動的ポート** ] フィールドをオフにします。</span><span class="sxs-lookup"><span data-stu-id="63626-150">Clear the **TCP Dynamic Ports** field for all IP addresses.</span></span> <span data-ttu-id="63626-151">フィールドにゼロ文字が含まれている場合は、SQL Server が動的ポートをリッスンしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="63626-151">If the field contains a zero character, then it means SQL Server is listening on dynamic ports.</span></span> <span data-ttu-id="63626-152">これらのフィールドがクリアされていて、ゼロが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63626-152">Make sure these fields are cleared and do not contain a zero.</span></span>

6.  <span data-ttu-id="63626-153">Lync Server がデータベースへの接続に使用する IP アドレスについては、次の図に示すように、[ **有効** **] が [はい]** に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63626-153">For the IP address that Lync Server will be using to connect to the database, make sure that **Enabled** is set to **Yes**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-154">![正しい IP に対して [はい] として有効に設定します。](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "正しい IP に対して [はい] として有効に設定します。")</span><span class="sxs-lookup"><span data-stu-id="63626-154">![Set enabled as Yes for the correct IP.](images/Dn776290.7f818b91-0793-4594-8932-90447270fad9(OCS.15).jpg "Set enabled as Yes for the correct IP.")</span></span>

7.  <span data-ttu-id="63626-155">ダイアログの下部にある [ **Ipall** ] セクションで、次の図に示すように、[ **TCP ポート** ] フィールドに目的のポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="63626-155">In the **IPAll** section at the bottom of the dialog, enter the desired port in the **TCP Port** field, as shown in the following figure.</span></span> <span data-ttu-id="63626-156">この例ではポート50062を使用していますが、49152と65535の間で任意のポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63626-156">In this example, we use port 50062, but you can use any port between 49152 and 65535.</span></span> <span data-ttu-id="63626-157">これらは動的およびプライベートの使用に割り当てられているポートであり、これにより、Lync Server 2013 の展開で使用されている他のポートと競合することはありません。</span><span class="sxs-lookup"><span data-stu-id="63626-157">These are the ports assigned to dynamic and private use, and this ensures you won’t conflict with other ports being used in the Lync Server 2013 deployment.</span></span>
    
    <span data-ttu-id="63626-158">![IPAll セクションのポートを設定します。](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "IPAll セクションのポートを設定します。")</span><span class="sxs-lookup"><span data-stu-id="63626-158">![Set port in IPAll section.](images/Dn776290.b5af53e2-7961-4664-b586-3ca8f3a17f06(OCS.15).jpg "Set port in IPAll section.")</span></span>

8.  <span data-ttu-id="63626-159">[ **OK]** を選択して、[Tcp/ip のプロパティ] ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="63626-159">Choose **OK** to exit the TCP/IP Properties dialog.</span></span>

9.  <span data-ttu-id="63626-160">Sql server 構成マネージャーの左側のウィンドウで、[ **Sql Server サービス** ] を選択して、sql server インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="63626-160">Restart the SQL Server instance by selecting **SQL Server Services** in the left pane of SQL Server Configuration Manager.</span></span> <span data-ttu-id="63626-161">次の図に示すように、右側のウィンドウで [ **SQL Server \<instance name\> \*\* ] を右クリックし、[**再起動\*\*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-161">Then right-click **SQL Server \<instance name\>** in the right pane, and select **Restart**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-162">![インスタンスの SQL Server サービスをリセットします。](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "インスタンスの SQL Server サービスをリセットします。")</span><span class="sxs-lookup"><span data-stu-id="63626-162">![Reset the SQL Server service for instance.](images/Dn776290.a965c8cf-f769-4b52-bb38-c48a438cf491(OCS.15).jpg "Reset the SQL Server service for instance.")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63626-163">新しい SQL Server ポートに対応するように、ファイアウォールの設定を更新してください。</span><span class="sxs-lookup"><span data-stu-id="63626-163">Make sure you update your firewall settings to accommodate the new SQL Server port.</span></span>



</div>

<span data-ttu-id="63626-164">**SQL Server のエイリアスを作成して構成する**</span><span class="sxs-lookup"><span data-stu-id="63626-164">**Create and Configure a SQL Server Alias**</span></span>

1.  <span data-ttu-id="63626-165">次の図に示すように、[ **スタート**] を選択し、[ **SQL Server 構成マネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-165">Select **Start**, and choose **SQL Server Configuration Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-166">![SQL Server Management Studio アイコン](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "SQL Server Management Studio アイコン")</span><span class="sxs-lookup"><span data-stu-id="63626-166">![The SQL Server Management Studio icon](images/Dn776290.6e811f27-cea9-4437-b44c-55bff013150f(OCS.15).png "The SQL Server Management Studio icon")</span></span>

2.  <span data-ttu-id="63626-167">次の図に示すように、左側のウィンドウで、[ **Sql Server インスタンス**] を選択し、[ **sql Native Client \<version\> 構成**] を選択してから、[ **エイリアス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-167">In the left pane, choose to expand **SQL Server instance**, choose to expand **SQL Native Client \<version\> Configuration**, and then choose **Aliases**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-168">![SQL Server 構成マネージャーのエイリアス。](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "SQL Server 構成マネージャーのエイリアス。")</span><span class="sxs-lookup"><span data-stu-id="63626-168">![Aliases in SQL Server Configuration Manager.](images/Dn776290.95341826-55d7-425f-ae19-d47d6668c5d8(OCS.15).jpg "Aliases in SQL Server Configuration Manager.")</span></span>

3.  <span data-ttu-id="63626-169">[ **エイリアス**] を右クリックし、[ **新しいエイリアス...**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-169">Right-click **Aliases**, and select **New Alias…**.</span></span>

4.  <span data-ttu-id="63626-170">次の図に示すように、 **エイリアス名**、 **ポート番号**、 **プロトコル**、および **サーバー**を入力します。</span><span class="sxs-lookup"><span data-stu-id="63626-170">Enter the **Alias Name**, **Port Number**, **Protocol**, and **Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-171">![新しいエイリアスを作成する](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "新しいエイリアスを作成する")</span><span class="sxs-lookup"><span data-stu-id="63626-171">![Creating a new alias](images/Dn776290.03653588-aecf-4fdd-b58a-95f5b372d478(OCS.15).jpg "Creating a new alias")</span></span>
    
    <div>
    

    > [!CAUTION]  
    > <span data-ttu-id="63626-172">前の手順で使用したのと同じ非標準ポートを入力してください。これは、SQL Server がリッスンするポートです。</span><span class="sxs-lookup"><span data-stu-id="63626-172">Make sure to enter the same non-standard port you used in the previous step since that is the port SQL Server will be listening on.</span></span> <span data-ttu-id="63626-173">構成されたエイリアスが正しくない SQL Server の FQDN またはインスタンスに接続している場合は、関連付けられているネットワークプロトコルを無効にしてから再び有効にします。</span><span class="sxs-lookup"><span data-stu-id="63626-173">If a configured alias is connecting to the wrong SQL Server FQDN or Instance, disable and then re-enable the associated network protocol.</span></span> <span data-ttu-id="63626-174">これにより、キャッシュされた接続情報がクリアされ、クライアントが正常に接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="63626-174">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>

    
    </div>

<span data-ttu-id="63626-175">**DNS CNAME リソースレコードを作成する**</span><span class="sxs-lookup"><span data-stu-id="63626-175">**Create a DNS CNAME Resource Record**</span></span>

1.  <span data-ttu-id="63626-176">DNS を管理しているコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="63626-176">Sign into the computer managing DNS.</span></span>

2.  <span data-ttu-id="63626-177">次の図に示すように、[ **スタート**] を選択し、[ **サーバーマネージャー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-177">Select **Start**, and choose **Server Manager**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-178">![サーバーマネージャーを開く](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "サーバーマネージャーを開く")</span><span class="sxs-lookup"><span data-stu-id="63626-178">![Opening Server Manager](images/Dn776290.3e4bd8ad-2a65-4a05-af40-c8dd3583bc8f(OCS.15).jpg "Opening Server Manager")</span></span>

3.  <span data-ttu-id="63626-179">次の図に示すように、[ **ツール** ] ドロップダウンを選択し、[ **DNS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-179">Choose the **Tools** drop-down, and select **DNS**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-180">![サーバーマネージャーから DNS を開く。](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "サーバーマネージャーから DNS を開く。")</span><span class="sxs-lookup"><span data-stu-id="63626-180">![Opening DNS from Server Manager.](images/Dn776290.415e1da1-7c9a-4a4e-a896-ca34a76aaeff(OCS.15).jpg "Opening DNS from Server Manager.")</span></span>

4.  <span data-ttu-id="63626-181">左側のウィンドウで、[サーバー名] ノードを展開し、[前方参照ゾーン] ノードを展開して、該当するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-181">In the left pane, expand the server name node, expand the Forward Lookup Zones node, and choose the relevant domain.</span></span>

5.  <span data-ttu-id="63626-182">次の図に示すように、ドメインを右クリックし、[ **新しいエイリアス (CNAME)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-182">Right-click the domain, and select **New Alias (CNAME)…**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-183">![新しいエイリアス CNAME を作成するためのオプションの選択](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "新しいエイリアス CNAME を作成するためのオプションの選択")</span><span class="sxs-lookup"><span data-stu-id="63626-183">![Selecting option to create a new alias CNAME](images/Dn776290.abe66cca-b53c-427a-9094-1a59dc6840ca(OCS.15).jpg "Selecting option to create a new alias CNAME")</span></span>

6.  <span data-ttu-id="63626-184">次の図に示すように、 **SQL Server の\*\*\*\*エイリアス名**と FQDN を入力します。</span><span class="sxs-lookup"><span data-stu-id="63626-184">Enter the **Alias Name** and the **FQDN for SQL Server**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-185">![[新しいエイリアスの CNAME] ダイアログに記入します。](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "[新しいエイリアスの CNAME] ダイアログに記入します。")</span><span class="sxs-lookup"><span data-stu-id="63626-185">![Filling in the new alias CNAME dialog.](images/Dn776290.dd0ebd2d-3407-4459-8bd9-2b389a7bc440(OCS.15).jpg "Filling in the new alias CNAME dialog.")</span></span>

7.  <span data-ttu-id="63626-186">**[OK]** を選択して CNAME を保存し、DNS マネージャーで表示します。</span><span class="sxs-lookup"><span data-stu-id="63626-186">Choose **OK** to save the CNAME and view it in DNS Manager.</span></span>

</div>

<div>

## <a name="validate-database-connectivity"></a><span data-ttu-id="63626-187">データベース接続を検証する</span><span class="sxs-lookup"><span data-stu-id="63626-187">Validate Database Connectivity</span></span>

<span data-ttu-id="63626-188">動作していることを確認するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="63626-188">There are many different ways to make sure it is working.</span></span> <span data-ttu-id="63626-189">SQL Server データベースが、エイリアスを使用して指定されたポートでリッスンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63626-189">You want to make sure that the SQL Server database is listening on the specified port using the alias.</span></span> <span data-ttu-id="63626-190">クイックチェックは、 **netstat** コマンドと **telnet** コマンドを使用して完了できます。</span><span class="sxs-lookup"><span data-stu-id="63626-190">A quick check can be completed using the **netstat** and **telnet** commands.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63626-191">Telnet クライアントは Windows Server に付属している機能ですが、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63626-191">Telnet Client is a Feature that comes with Windows Server but that must be installed.</span></span> <span data-ttu-id="63626-192">Windows Server の機能をインストールするには、サーバーマネージャーを開き、[管理] メニューの [役割と機能の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63626-192">A Windows Server Feature can be installed by opening Server Manager and selecting Add Roles and Features from the Manage menu.</span></span>



</div>

<span data-ttu-id="63626-193">**Netstat および telnet を使用してデータベース接続を確認する**</span><span class="sxs-lookup"><span data-stu-id="63626-193">**Use netstat and telnet to verify database connectivity**</span></span>

1.  <span data-ttu-id="63626-194">[ **スタート**] を選択し、コマンドプロンプトを開くために「 **cmd** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="63626-194">Select **Start**, and type **cmd** to open a command prompt.</span></span>

2.  <span data-ttu-id="63626-195">「 **Netstat-a-f**」と入力し、次の図に示すように、SQL Server が正しいポートを使用して実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63626-195">Type **netstat -a -f**, and confirm that SQL Server is running with the correct port, as shown in the following figure.</span></span>
    
    <span data-ttu-id="63626-196">![Netstat を使用してポートを確認する。](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Netstat を使用してポートを確認する。")</span><span class="sxs-lookup"><span data-stu-id="63626-196">![Using netstat to verify port.](images/Dn776290.4ff3a1b2-c5eb-4496-8be7-374c351fa027(OCS.15).jpg "Using netstat to verify port.")</span></span>

3.  <span data-ttu-id="63626-197">「 \*\*Telnet \<alias name\> \<port \#\> \*\* 」と入力して、SQL Server インスタンスへの接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="63626-197">Type **telnet \<alias name\> \<port \#\>** to confirm the connection to the SQL Server instance.</span></span> <span data-ttu-id="63626-198">接続に成功すると、telnet が接続され、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="63626-198">If the connection is successful, telnet will connect and you shouldn’t see an error.</span></span> <span data-ttu-id="63626-199">これは、SQL Server インスタンスが正しいエイリアスで適切なポートをリッスンしていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="63626-199">This shows that the SQL Server instance is listening on the correct port with the correct alias.</span></span> <span data-ttu-id="63626-200">SQL Server データベースへの接続で問題が発生した場合は、接続を確立できないというエラーが telnet に表示されます。</span><span class="sxs-lookup"><span data-stu-id="63626-200">If there’s a problem connecting to the SQL Server database, then telnet shows an error that the connection cannot be made.</span></span> <span data-ttu-id="63626-201">データベースサーバーでデータベース接続を確認したので、Lync Server (ネットワーク経由) から同じことを行うことができます。また、アクセスをブロックしているファイアウォールがないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="63626-201">Now that you have checked database connectivity on the database server, you can do the same thing from Lync Server (over the network) and make sure there aren’t any firewalls blocking access along the way.</span></span>

</div>

<div>

## <a name="conclusion"></a><span data-ttu-id="63626-202">まとめ</span><span class="sxs-lookup"><span data-stu-id="63626-202">Conclusion</span></span>

<span data-ttu-id="63626-203">SQL Server のエイリアスを構成したら、それを使用して、トポロジビルダーツールで Lync Server 2013 トポロジを作成できます。</span><span class="sxs-lookup"><span data-stu-id="63626-203">Once the SQL Server alias has been configured, you can use it to create a Lync Server 2013 topology in the Topology Builder tool.</span></span> <span data-ttu-id="63626-204">トポロジの詳細については、「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63626-204">For more information about topologies, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63626-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="63626-205">See Also</span></span>


<span data-ttu-id="63626-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md)  
[Lync Server 2013 でのセキュリティの計画](lync-server-2013-planning-for-security.md)</span><span class="sxs-lookup"><span data-stu-id="63626-206">[Microsoft Lync Server 2013](microsoft-lync-server-2013.md) 
[Planning for security in Lync Server 2013](lync-server-2013-planning-for-security.md)</span></span>  
[<span data-ttu-id="63626-207">Lync Server 2013 でのトポロジの定義と構成</span><span class="sxs-lookup"><span data-stu-id="63626-207">Defining and configuring the topology in Lync Server 2013</span></span>](lync-server-2013-defining-and-configuring-the-topology.md)  
[<span data-ttu-id="63626-208">Lync Server 2013 の展開 </span><span class="sxs-lookup"><span data-stu-id="63626-208">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

