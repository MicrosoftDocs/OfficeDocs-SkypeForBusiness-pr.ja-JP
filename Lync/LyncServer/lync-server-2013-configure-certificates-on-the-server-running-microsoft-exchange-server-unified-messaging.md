---
title: 'Lync Server 2013: Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="a67b4-102">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="a67b4-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a67b4-103">_**最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a67b4-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a67b4-104">Exchange ユニファイドメッセージング (UM) を展開している場合、計画ドキュメントの「 [Lync Server 2013 での Exchange ユニファイドメッセージングの統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」で説明されているように、組織内のエンタープライズ voip 機能を提供するには、次の手順を使用して、exchange um を実行しているサーバーで証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a67b4-105">内部証明書の場合、Lync Server 2013 を実行しているサーバーと、Microsoft Exchange を実行しているサーバーの両方が、相互に信頼されている信頼できるルート証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b4-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="a67b4-106">証明機関 (CA) は、信頼されたルート機関の証明書ストアに証明機関のルート証明書が登録されている限り、同じまたは別の証明機関とすることができます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="a67b4-107">Lync Server 2013 に接続するには、Exchange Server がサーバー証明書を使用して構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b4-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="a67b4-108">Exchange サーバーの CA 証明書をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="a67b4-109">Exchange サーバーの CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="a67b4-110">CA が Exchange Server の信頼されているルート Ca のリストに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="a67b4-111">Exchange Server の証明書要求を作成して、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="a67b4-112">Exchange Server の証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="a67b4-113">CA 証明書をダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="a67b4-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="a67b4-114">Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックし**て、発行 CA サーバー\<\>の Http://の名前**を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="a67b4-115">[**タスクの選択**] で、[ **CA 証明書、証明書チェーン、または CRL をダウンロード**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="a67b4-116">**Ca 証明書、証明書チェーン、または CRL**をダウンロード**するに**は、[エンコード方法] を [ベース 64] に、[ **ca 証明書のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67b4-117">この手順では、識別エンコード規則 (DER) のエンコードを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="a67b4-118">DER エンコードを選択した場合は、この手順の次の手順のファイルの種類と、 <STRONG>CA 証明書をインストールする</STRONG>手順10については .cer ではなく. p7b を使用します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="a67b4-119">[**ファイルのダウンロード**] ダイアログボックスで、[**保存**] をクリックし、サーバーのハードディスクにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="a67b4-120">(前の手順で選んだエンコードに応じて、ファイル拡張子は .cer または. p7b のいずれかになります)。</span><span class="sxs-lookup"><span data-stu-id="a67b4-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="a67b4-121">CA 証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="a67b4-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="a67b4-122">Exchange UM を実行しているサーバーで、[**スタート**]、[**実行**]、[**名前**を指定して実行 **] の順にクリック**し、[ **OK**] をクリックして、Microsoft 管理コンソール (mmc) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="a67b4-123">[**ファイル**] メニューで、[スナップインの**追加と削除**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="a67b4-124">[**スタンドアロンスナップ**インの追加] ボックスで、[**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="a67b4-125">[**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="a67b4-126">**[コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター: (このコンソールが実行されているコンピューター)** ] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="a67b4-127">[**閉じる**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="a67b4-128">コンソールツリーで、[**証明書 (ローカルコンピューター)**]、[**信頼されたルート証明機関**] の順に展開し、[**証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="a67b4-129">[**証明書**] を右クリックし、[**すべてのタスク**] をクリックして、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="a67b4-130">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-130">Click **Next**.</span></span>

10. <span data-ttu-id="a67b4-131">[**参照**] をクリックしてファイルを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="a67b4-132">(手順3で選択したエンコード方法によって、 **CA 証明書をダウンロードする**場合は、.cer または. p7b のファイル拡張子のいずれかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="a67b4-133">[**証明書をすべて次のストアに配置する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="a67b4-134">[**参照**] をクリックし、[**信頼されたルート証明機関**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="a67b4-135">[**次へ**] をクリックして設定を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="a67b4-136">CA が信頼されたルート Ca のリストに含まれていることを確認するには</span><span class="sxs-lookup"><span data-stu-id="a67b4-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="a67b4-137">Exchange UM を実行しているサーバーで、MMC で [**証明書 (ローカルコンピューター)**]、[**信頼されたルート証明機関**] の順に展開し、[**証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="a67b4-138">[詳細] ウィンドウで、CA が信頼できる Ca の一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="a67b4-139">Exchange Server 2013 UM を Lync Server と共に構成するには</span><span class="sxs-lookup"><span data-stu-id="a67b4-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="a67b4-140">詳細については、Exchange Server のドキュメントの「Exchange 2013 UM と Lync Server の[http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)統合」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67b4-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="a67b4-141">証明書の要求を作成し、Exchange Server 2007 (SP1) で証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="a67b4-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="a67b4-142">Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックして、発行**\>CA サーバーの** **\<http://** の名前を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="a67b4-143">[**タスクの選択**] の [**証明書の要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="a67b4-144">[**証明書の要求**] で [**証明書の要求の詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="a67b4-145">[ **Advanced Certificate request**] の下で、[**作成してこの CA に要求を送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="a67b4-146">[ **Advanced Certificate Request**] で、[ **Web サーバー**またはサーバー認証用に構成された別のサーバー証明書テンプレート] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="a67b4-147">[**オフラインテンプレートの識別情報**] の [**名前**] ボックスに、Exchange サーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67b4-148">通信を機能させるには、Exchange Server の FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b4-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="a67b4-149">[**キーのオプション**] で、[**ローカルコンピューターの証明書ストアに証明書を格納**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="a67b4-150">Web ページの下部にある [**送信**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="a67b4-151">確認を求めるダイアログボックスが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="a67b4-152">[発行された証明書] ページで、[**証明書の発行**] の [**この証明書のインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="a67b4-153">確認を求めるダイアログボックスが表示されたら、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="a67b4-154">"新しい証明書が正常にインストールされました。" というメッセージが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="a67b4-155">Exchange Server 2010 で証明書を作成するには</span><span class="sxs-lookup"><span data-stu-id="a67b4-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="a67b4-156">適切なユーザー権限を持つ Exchange UM を実行しているサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="a67b4-157">詳細については、の「クライアントアクセス[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)許可」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67b4-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="a67b4-158">証明書を作成するには、次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67b4-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="a67b4-159">"新しい Exchange 証明書を作成する"[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="a67b4-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="a67b4-160">"Exchange 証明書をインポートする"[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="a67b4-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67b4-161">証明書の<STRONG>サブジェクト名</STRONG>については、通信を機能させるために Exchange SERVER の FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b4-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="a67b4-162">Exchange Server 2007 (SP1) で証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="a67b4-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="a67b4-163">Exchange UM を実行しているサーバーで、MMC を開きます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="a67b4-164">コンソールツリーで、[**個人**] を展開し、[**証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="a67b4-165">[詳細] ウィンドウで、[個人証明書] が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="a67b4-166">証明書をダブルクリックして詳細を確認し、それが有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67b4-167">証明書が有効として表示されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a67b4-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="a67b4-168">Microsoft Exchange ユニファイドメッセージングサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a67b4-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67b4-169">Exchange Server 2007 SP1 ユニファイドメッセージングを実行しているサーバーでは、適切な証明書が自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="a67b4-170">イベントビューアーを開き、イベント ID 1112 を探します。これにより、Exchange Server 2007 SP1 ユニファイドメッセージングが実行されているサーバーがどの証明書を取得したかが指定されます。</span><span class="sxs-lookup"><span data-stu-id="a67b4-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="a67b4-171">Exchange Server 2010 で証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="a67b4-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="a67b4-172">適切なユーザー権限を持つ Exchange UM を実行しているサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a67b4-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="a67b4-173">詳細については、の「クライアントアクセス[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)許可」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67b4-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="a67b4-174">証明書を割り当てる手順については、の「証明書にサービスを[http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a67b4-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

