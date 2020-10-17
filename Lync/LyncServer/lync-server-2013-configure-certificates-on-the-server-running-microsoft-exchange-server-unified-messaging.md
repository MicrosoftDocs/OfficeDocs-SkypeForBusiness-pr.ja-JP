---
title: 'Lync Server 2013: Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーでの証明書の構成'
description: 'Lync Server 2013: Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成します。'
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
ms.openlocfilehash: 0a7d1e0aec3ec36723ee68c0a1dcd7f60050f9ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564403"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="53bc0-103">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="53bc0-103">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53bc0-104">_**トピックの最終更新日:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="53bc0-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="53bc0-105">「計画」のドキュメントの「 [Lync Server 2013 での Exchange ユニファイドメッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 」で説明されているように、Exchange ユニファイドメッセージング (UM) を展開している場合、exchange um の機能を組織内のエンタープライズ voip ユーザーに提供するには、次の手順を使用して、exchange um を実行しているサーバーで証明書を</span><span class="sxs-lookup"><span data-stu-id="53bc0-105">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="53bc0-106">内部証明書の場合、Lync Server 2013 を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方が、相互に信頼された信頼できるルート証明機関の証明書を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bc0-106">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="53bc0-107">証明機関 (CA) は、サーバーが信頼されたルート証明機関の証明書ストアに登録されている証明機関のルート証明書を持っている限り、同一または別の証明機関にすることができます。</span><span class="sxs-lookup"><span data-stu-id="53bc0-107">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="53bc0-108">Lync Server 2013 に接続するためには、サーバー証明書を使用して Exchange サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bc0-108">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="53bc0-109">Exchange Server の CA 証明書をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-109">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="53bc0-110">Exchange Server の CA 証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-110">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="53bc0-111">CA が、Exchange Server の信頼されたルート証明機関一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-111">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="53bc0-112">Exchange Server の証明書要求を作成し、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-112">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="53bc0-113">Exchange Server の証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="53bc0-113">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="53bc0-114">CA 証明書をダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="53bc0-114">To download the CA certificate</span></span>

1.  <span data-ttu-id="53bc0-115">Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックします。「http://があります」と入力し、[ **OK**] をクリックします。 \*\* \<name of your Issuing CA Server\> \*\*</span><span class="sxs-lookup"><span data-stu-id="53bc0-115">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="53bc0-116">**[タスクの選択]** の **[CA 証明書、証明書チェーン、または CRL のダウンロード]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-116">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="53bc0-117">[ **Ca 証明書、証明書チェーン、または CRL のダウンロード**] の [ **Base 64 にエンコード方法**] を選択し、[ **ca 証明書のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-117">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53bc0-118">この手順では、識別エンコードルール (DER) エンコードを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="53bc0-118">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="53bc0-119">DER エンコードを選択する場合は、この手順の次のステップと「<STRONG>CA 証明書をインストールするには</STRONG>」のステップ 10 のファイル タイプが .cer ではなく、.p7b になります。</span><span class="sxs-lookup"><span data-stu-id="53bc0-119">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="53bc0-p103">**[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックし、ファイルをサーバー上のハード ディスクに保存します。(このファイルの拡張子は、前のステップで選択したエンコードに応じて、.cer または .p7b となります。)</span><span class="sxs-lookup"><span data-stu-id="53bc0-p103">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="53bc0-122">CA 証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="53bc0-122">To install the CA certificate</span></span>

1.  <span data-ttu-id="53bc0-123">Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックして、[**開く**] ボックスに「 **MMC** 」と入力し、[ **OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。</span><span class="sxs-lookup"><span data-stu-id="53bc0-123">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="53bc0-124">**[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-124">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="53bc0-125">**[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-125">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="53bc0-126">**[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-126">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="53bc0-127">[ **コンピューターの選択** ] ダイアログボックスで、[ **ローカルコンピューター: (このコンソールを実行しているコンピューター)** ] チェックボックスがオンになっていることを確認し、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-127">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="53bc0-128">**[閉じる]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-128">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="53bc0-129">コンソール ツリーで、**[証明書 (ローカル コンピューター)]** を展開し、**[信頼されたルート証明機関]** を展開して **[証明書]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-129">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="53bc0-130">**[証明書]** を右クリックし、**[すべてのタスク]** をクリックして **[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-130">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="53bc0-131">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-131">Click **Next**.</span></span>

10. <span data-ttu-id="53bc0-p104">**[参照]** をクリックしてファイルを特定し、**[次へ]** をクリックします。(このファイルの拡張子は、「**CA 証明書をダウンロードするには**」のステップ 3 で選択したエンコードに応じて、.cer または .p7b となります。)</span><span class="sxs-lookup"><span data-stu-id="53bc0-p104">Click **Browse** to locate the file, and then click **Next**. (The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="53bc0-134">\*\*[証明書をすべて次のストアに配置する] \*\*をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-134">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="53bc0-135">**[参照]** をクリックし、**[信頼されたルート証明機関]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-135">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="53bc0-136">**[次へ]** をクリックし、設定を確認して、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-136">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="53bc0-137">CA が信頼されたルート証明機関の一覧にあることを確認するには</span><span class="sxs-lookup"><span data-stu-id="53bc0-137">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="53bc0-138">Exchange UM を実行しているサーバーで、MMC の [ **証明書 (ローカルコンピューター)**] を展開し、[ **信頼されたルート証明機関**] を展開して、[ **証明書**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-138">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="53bc0-139">詳細ウィンドウで、CA が、信頼されたルート証明機関の一覧にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-139">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="53bc0-140">Lync Server を使用して Exchange Server 2013 UM を構成するには</span><span class="sxs-lookup"><span data-stu-id="53bc0-140">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="53bc0-141">詳細については、Exchange Server のドキュメントの「」の「Exchange 2013 UM と Lync Server の統合」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。</span><span class="sxs-lookup"><span data-stu-id="53bc0-141">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="53bc0-142">証明書要求を作成して、証明書を Exchange Server 2007 (SP1) にインストールするには</span><span class="sxs-lookup"><span data-stu-id="53bc0-142">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="53bc0-143">Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックします。「http://があります」と入力し、[ **OK**] をクリックします。 \*\* \<**name of your Issuing CA Server**\> \*\*</span><span class="sxs-lookup"><span data-stu-id="53bc0-143">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<**name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="53bc0-144">**[タスクの選択]** で **[証明書の要求]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-144">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="53bc0-145">**[証明書の要求]** で **[証明書の要求の詳細設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-145">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="53bc0-146">**[証明書の要求の詳細設定]** で **[この CA への要求を作成し送信する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-146">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="53bc0-147">**[証明書の要求の詳細設定]** で、サーバー認証用に構成された **[Web サーバー]** 証明書テンプレートまたは別のサーバー証明書テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-147">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="53bc0-148">[ **オフラインテンプレート用の識別情報**] の [ **名前** ] ボックスに、Exchange サーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-148">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53bc0-149">通信を可能にするには、Exchange Server の FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bc0-149">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="53bc0-150">**[キーのオプション]** で **[ローカル コンピューターの証明書ストアに証明書を格納する]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-150">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="53bc0-151">Web ページの下部にある **[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-151">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="53bc0-152">確認のダイアログ ボックスで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-152">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="53bc0-153">[証明書は発行されました] ページの **[証明書は発行されました]** で **[この証明書のインストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-153">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="53bc0-154">確認のダイアログ ボックスで、**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-154">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="53bc0-155">"新しい証明書は正しくインストールされました" というメッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-155">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="53bc0-156">Exchange Server 2010 で証明書を作成するには</span><span class="sxs-lookup"><span data-stu-id="53bc0-156">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="53bc0-157">Exchange UM を実行しているサーバーに適切なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-157">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="53bc0-158">詳細については、「」の「クライアントアクセス許可」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) 。</span><span class="sxs-lookup"><span data-stu-id="53bc0-158">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="53bc0-159">証明書を作成するには、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53bc0-159">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="53bc0-160">「新しい Exchange 証明書を作成する」 [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="53bc0-160">"Create a New Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="53bc0-161">「Exchange 証明書をインポートする」 [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="53bc0-161">"Import an Exchange Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53bc0-162">通信を可能にするには、証明書の <STRONG>[サブジェクト名]</STRONG> に、Exchange Server の FQDN を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bc0-162">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="53bc0-163">Exchange Server 2007 (SP1) に証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="53bc0-163">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="53bc0-164">Exchange UM を実行しているサーバーで、MMC を開きます。</span><span class="sxs-lookup"><span data-stu-id="53bc0-164">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="53bc0-165">コンソール ツリーで **[個人]** を展開し、**[証明書]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-165">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="53bc0-166">詳細ウィンドウに個人の証明書が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-166">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="53bc0-167">証明書をダブルクリックして詳細を表示し、有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-167">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53bc0-168">証明書に有効と表示されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="53bc0-168">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="53bc0-169">Microsoft Exchange ユニファイド メッセージング サービスを再開します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-169">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53bc0-170">Exchange Server 2007 SP1 ユニファイド メッセージングを実行しているサーバーで、正しい証明書が自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="53bc0-170">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="53bc0-171">イベント ビューアを開き、イベント ID 1112 を探します。このイベントは、Exchange Server 2007 SP1 ユニファイド メッセージングを実行しているサーバーが取得した証明書を示します。</span><span class="sxs-lookup"><span data-stu-id="53bc0-171">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="53bc0-172">Exchange Server 2010 に証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="53bc0-172">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="53bc0-173">Exchange UM を実行しているサーバーに適切なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="53bc0-173">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="53bc0-174">詳細については、「」の「クライアントアクセス許可」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) 。</span><span class="sxs-lookup"><span data-stu-id="53bc0-174">For details, see "Client Access Permissions" at [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="53bc0-175">証明書を割り当てる手順については、「サービスを証明書に割り当てる」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) 。</span><span class="sxs-lookup"><span data-stu-id="53bc0-175">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

