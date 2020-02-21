---
title: 'Lync Server 2013: 内部エッジインターフェイス用の証明書の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34e1d0d4e87bffbf28ba600ab23d849fd664423
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="a6e90-102">Lync Server 2013 での内部エッジインターフェイス用の証明書の設定</span><span class="sxs-lookup"><span data-stu-id="a6e90-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6e90-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="a6e90-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a6e90-104">証明書ウィザードを実行する場合、使用する証明書テンプレートの種類に対して適切なアクセス許可が割り当てられたグループのメンバーであるアカウントを使用してログインしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6e90-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="a6e90-105">既定では、Lync Server 2013 証明書要求は Web サーバー証明書テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="a6e90-106">RTCUniversalServerAdmins グループのメンバーであるアカウントおよびこのテンプレートを使用して証明書を要求する場合、そのテンプレートを使用するために必要な登録アクセス許可がそのグループに割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a6e90-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="a6e90-107">各エッジサーバーの内部インターフェイスに1つの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="a6e90-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="a6e90-108">内部インターフェイスの証明書は、内部のエンタープライズ証明機関 (CA) またはパブリック CA によって発行できます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="a6e90-109">組織で内部 CA が展開されている場合は、内部 CA を使用して内部インターフェイス用の証明書を発行することによって、公開証明書を使用する費用を節約できます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="a6e90-110">内部 Windows Server 2008 CA または Windows Server 2008 R2 CA を使用して、これらの証明書を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="a6e90-111">この他の証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e90-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="a6e90-112">サイトの内部エッジインターフェイスで証明書を設定するには、このセクションの手順を使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6e90-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="a6e90-113">内部インターフェイス用の CA 証明書チェーンを各エッジサーバーにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="a6e90-114">各エッジサーバーに、内部インターフェイス用の CA 証明書チェーンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="a6e90-115">1台のエッジサーバー (最初のエッジサーバー) で、内部インターフェイス用の証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="a6e90-116">最初のエッジサーバーの内部インターフェイスの証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="a6e90-117">このサイトの他のエッジサーバー (またはこのロードバランサーの背後に展開されている) で証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="a6e90-118">各エッジサーバーの内部インターフェイスの証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="a6e90-119">エッジサーバー (複数サイトエッジトポロジ) に複数のサイトがある場合、または異なるロードバランサーの背後に展開されたエッジサーバーの別個のセットを使用している場合は、エッジサーバーを持つ各サイトに対して、エッジサーバーのセットごとに次の手順を実行する必要があります。別のロードバランサーの背後に展開されます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a6e90-120">このセクションの手順の手順は、Windows Server&nbsp;2008 CA、windows server&nbsp;2008&nbsp;R2 ca、windows Server 2012 CA、または windows server 2012 R2 ca を使用して、各エッジサーバーの証明書を作成する方法に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a6e90-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="a6e90-121">その他の CA の詳細な手順については、その CA のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6e90-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="a6e90-122">既定では、認証されたすべてのユーザーが、証明書を要求するための適切なユーザー権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="a6e90-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="a6e90-123">このセクションの手順は、エッジサーバーの展開プロセスの一環として、エッジサーバー上に証明書要求を作成することに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a6e90-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="a6e90-124">フロントエンドサーバーを使用して証明書要求を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="a6e90-125">この操作は、エッジサーバーの展開を開始する前に、計画と展開のプロセスの早い段階で証明書要求を完了するために行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="a6e90-126">これを行うには、要求する証明書が、エクスポート可能な秘密キーで定義されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e90-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="a6e90-127">このセクションの手順では、証明書の .cer ファイルと. p7b ファイルを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="a6e90-128">別の種類のファイルを使用する場合は、必要に応じてこれらの手順を変更します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="a6e90-129">Certsrv Web サイトを使用して内部インターフェイス用の CA 証明書チェーンをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="a6e90-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="a6e90-130">内部ネットワーク (エッジサーバーではない) の Lync Server 2013 サーバーに**Administrators**グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="a6e90-131">[**スタート**]、[**実行**] の順にクリックし、次のコマンドを入力して、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="a6e90-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6e90-133">Windows Server 2008 または Windows Server 2008 R2 エンタープライズ CA を使用している場合は、http ではなく https を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6e90-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="a6e90-134">発行元の CA の certsrv web ページで、[**タスクの選択**] の [ **CA 証明書、証明書チェーン、または CRL のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="a6e90-135">[ **Ca 証明書、証明書チェーン、または CRL のダウンロード**] の [ **ca 証明書チェーンのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="a6e90-136">**[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="a6e90-137">. P7b ファイルをサーバーのハードディスクドライブに保存し、各エッジサーバーのフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6e90-138">. P7b ファイルには、証明のパスにあるすべての証明書が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e90-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="a6e90-139">証明のパスを表示するには、サーバー証明書を開き、証明のパスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="a6e90-140">MMC を使用して内部インターフェイス用の CA 証明書チェーンをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a6e90-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="a6e90-141">Microsoft 管理コンソール (MMC) を使用して、任意のドメインに参加しているコンピューターから CA ルート証明書をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="a6e90-142">[**スタート**] をクリックし、[**実行**] をクリックして、「 **MMC**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="a6e90-143">MMC コンソールで、[**ファイル**] をクリックし、[**追加/削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="a6e90-144">[**スナップインの追加と削除**] ダイアログボックスの一覧で、[**証明書**] を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="a6e90-145">メッセージが表示されたら、[**コンピューターアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="a6e90-146">[**コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="a6e90-147">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-147">Click **Finish**.</span></span> <span data-ttu-id="a6e90-148">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-148">Click **OK**.</span></span>

4.  <span data-ttu-id="a6e90-149">[**証明書 (ローカルコンピューター)**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="a6e90-150">[**信頼されたルート証明機関**] を展開し、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="a6e90-151">CA によって発行されたルート証明書をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="a6e90-152">証明書を右クリックし、[**すべてのタスク**] を選択して、[**エクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="a6e90-153">**証明書のエクスポートウィザード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="a6e90-154">**証明書のエクスポート ウィザード**で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="a6e90-155">[**エクスポートファイルの形式**] ダイアログで、エクスポート先の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="a6e90-156">**暗号化メッセージ構文標準-PKCS \#7 証明書 () をお勧めします。P7B)**。</span><span class="sxs-lookup"><span data-stu-id="a6e90-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="a6e90-157">[**暗号化メッセージ構文] \#標準-PKCS 7 証明書 (.P7B)** で、[証明の**パスにある証明書をすべて含める (可能な場合**)] チェックボックスをオンにして、ルート CA 証明書と中間 CA 証明書を含め、証明書チェーンをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="a6e90-158">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-158">Click **Next**.</span></span>

8.  <span data-ttu-id="a6e90-159">[ファイル名] エントリの [**エクスポートするファイル**] ダイアログで、エクスポートした証明書のパスとファイル名 (既定の拡張子は. p7b) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="a6e90-160">必要に応じて、[**参照**] をクリックして、エクスポートした証明書を配置するディレクトリを見つけ、エクスポートされた証明書の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="a6e90-161">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-161">Click **Save**.</span></span> <span data-ttu-id="a6e90-162">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-162">Click **Next**.</span></span>

9.  <span data-ttu-id="a6e90-163">操作の概要を確認し、[**完了**] をクリックして証明書のエクスポートを完了します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="a6e90-164">[ **OK]** をクリックして、正常にエクスポートされたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="a6e90-165">内部インターフェイス用の CA 証明書チェーンをインポートするには</span><span class="sxs-lookup"><span data-stu-id="a6e90-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="a6e90-166">各エッジサーバーで、[**スタート**] をクリックし、[名前を指定して**実行**] をクリックして、[**開く**] ボックスに「 **MMC** 」と入力し、[ **OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="a6e90-167">**[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="a6e90-168">**[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="a6e90-169">**[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="a6e90-170">**[コンピューターの選択]** ダイアログ ボックスで、**[ローカル コンピューター: (このコンソールを実行しているコンピューター)]** チェック ボックスがオンになっていることを確認して、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="a6e90-171">**[閉じる]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="a6e90-172">コンソールツリーで、[**証明書 (ローカルコンピューター)**] を展開し、[**信頼されたルート証明機関**] を右クリックし、[**すべてのタスク**] をポイントして、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="a6e90-173">ウィザードの [**インポートするファイル**] で、証明書のファイル名 (前の手順で、内部インターフェイス用の CA 証明書チェーンをダウンロードしたときに指定した名前) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="a6e90-174">各エッジサーバーでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="a6e90-175">内部インターフェイスの証明書要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="a6e90-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="a6e90-176">いずれかのエッジサーバーで、展開ウィザードを起動し、[**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6e90-177">プール内の1つの場所に複数のエッジサーバーがある場合は、いずれかのエッジサーバー上で証明書ウィザードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="a6e90-178">ステップ3を初めて実行した後、ボタンが<STRONG>再度実行</STRONG>されるように変更され、すべての必須証明書の要求、インストール、および割り当てが完了するまで、タスクが正常に完了したことを示す緑のチェックマークが表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6e90-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="a6e90-179">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="a6e90-180">**[証明書要求]** ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="a6e90-181">[**要求**の送信] ページで、[**要求を準備して後で送信**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="a6e90-182">[**証明書要求ファイル**] ページで、要求を保存する完全なパスとファイル名を入力します (たとえば、 **c:\\cert\_内部\_エッジ. .cer**)。</span><span class="sxs-lookup"><span data-stu-id="a6e90-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="a6e90-183">[**代替証明書テンプレートの指定**] ページで、既定の WebServer テンプレート以外のテンプレートを使用するには、[**選択した証明機関に別の証明書テンプレートを使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="a6e90-184">[**名前およびセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6e90-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="a6e90-185">[**フレンドリ名**] に、証明書の表示名 ([内部エッジ] など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="a6e90-186">**[ビット長]** で、ビット長を指定します (通常は既定値の **[2048]**)。</span><span class="sxs-lookup"><span data-stu-id="a6e90-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a6e90-187">ビット長が大きいほどセキュリティが向上しますが、速度に悪影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="a6e90-188">証明書をエクスポート可能にする必要がある場合は、[**証明書の秘密キーをエクスポート可能としてマーク**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="a6e90-189">[**組織情報**] ページで、組織の名前と組織単位 (OU) (部門や部署など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="a6e90-190">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="a6e90-191">[**サブジェクト名/サブジェクト代替名**] ページに、ウィザードによって自動的に設定される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="a6e90-192">[**追加のサブジェクト代替名の構成**] ページで、必要な追加のサブジェクトの別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="a6e90-193">[**要求の概要**] ページで、要求の生成に使用する証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="a6e90-194">コマンドが完了したら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="a6e90-195">証明書要求のログを表示するには、**[ログの表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="a6e90-196">証明書要求を完了するには、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="a6e90-197">**[証明書要求ファイル]** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a6e90-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="a6e90-198">生成した証明書の署名要求 (CSR) ファイルを表示するには、**[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="a6e90-199">ウィザードを閉じるには、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="a6e90-200">このファイルを CA に提出します (エンタープライズ CA の組織でサポートされている電子メールまたはその他の方法)。応答ファイルを受け取ったときに、このコンピューターに新しい証明書をコピーしてインポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="a6e90-201">内部インターフェイス用の証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="a6e90-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="a6e90-202">証明書要求を作成したエッジサーバーに、ローカルの Administrators グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="a6e90-203">展開ウィザードで、[**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**再実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="a6e90-204">ステップ3を初めて実行すると、ボタンが**再度実行**されますが、必要なすべての証明書の要求、インストール、および割り当てが完了するまで、緑のチェックマーク (タスクが正常に完了したことを示す) は表示されません。</span><span class="sxs-lookup"><span data-stu-id="a6e90-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="a6e90-205">[**利用可能な証明書タスク**] ページで、[a から証明書をインポートする] をクリックし**ます。P7b、.pfx、または .cer ファイル**。</span><span class="sxs-lookup"><span data-stu-id="a6e90-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="a6e90-206">[**証明書のインポート**] ページで、このエッジサーバーの内部インターフェイス用に要求して受信した証明書の完全なパスとファイル名を入力します (または、[**参照**] をクリックして、ファイルを見つけて選択します)。</span><span class="sxs-lookup"><span data-stu-id="a6e90-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="a6e90-207">プールの他のメンバーに対して秘密キーを含む証明書をインポートする場合は、[**証明書ファイルに証明書の秘密キーが含まれてい**ます] チェックボックスをオンにして、パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="a6e90-208">プール内のエッジ サーバー用の証明書と秘密キーをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="a6e90-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="a6e90-209">証明書をインポートしたのと同じエッジ サーバーに、Administrators グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="a6e90-210">[**スタート**] ボタン、[**ファイル名を指定して実行**] の順にクリックし、「**MMC**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="a6e90-211">MMC コンソールで、[**ファイル**] をクリックし、[**スナップインの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="a6e90-212">[スナップインの追加と削除] ページで、[**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="a6e90-213">[証明書スナップイン] ダイアログで、[**コンピューターアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="a6e90-214">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-214">Click **Next**.</span></span> <span data-ttu-id="a6e90-215">[コンピューターの選択] で、[**ローカルコンピューター: (このコンソールを実行しているコンピューター)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="a6e90-216">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-216">Click **Finish**.</span></span> <span data-ttu-id="a6e90-217">MMC コンソールの構成を完了するには、[ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="a6e90-218">[**証明書 (ローカルコンピューター)** ] をダブルクリックして、証明書ストアを展開します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="a6e90-219">[**個人**] をダブルクリックし、[**証明書**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a6e90-p116">ローカル コンピューターの個人の証明書ストアに証明書がない場合は、インポートした証明書に秘密キーが関連付けられていません。要求とインポートの手順を再確認してください。問題が解決しない場合は、証明機関の管理者またはプロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a6e90-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="a6e90-223">ローカルコンピューターの証明書個人用ストアで、エクスポートする証明書を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="a6e90-224">[**すべてのタスク**] をクリックし、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="a6e90-225">証明書のエクスポートウィザードで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="a6e90-226">[**はい、秘密キーをエクスポート**します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="a6e90-227">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6e90-p119">[<STRONG>はい、秘密キーをエクスポートします</STRONG>] が無効になっていて選択できない場合、この証明書に関連付けられている秘密キーはエクスポート可能になっていません。エクスポートを続行するには、その前に証明書を再度要求して、証明書の秘密キーをエクスポート可能にする必要があります。証明機関の管理者またはプロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a6e90-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="a6e90-231">[エクスポートファイルの形式] ダイアログで、[ **Personal Information Exchange\#– PKCS 12 (]) を選択します。PFX)** を選択し、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="a6e90-232">可能であれば、証明書パスにあるすべての証明書を含める</span><span class="sxs-lookup"><span data-stu-id="a6e90-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="a6e90-233">すべての拡張プロパティをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a6e90-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="a6e90-p120">エッジ サーバーから証明書をエクスポートするとき、[<STRONG>正しくエクスポートされたときは秘密キーを削除する</STRONG>] をオンにしないでください。このオプションをオンにすると、このエッジ サーバーに証明書と秘密キーをインポートすることが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a6e90-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="a6e90-236">続行するには、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="a6e90-237">秘密キーを保護するためにパスワードを割り当てる場合は、秘密キーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="a6e90-238">確認のためにパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="a6e90-239">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-239">Click **Next**.</span></span>

11. <span data-ttu-id="a6e90-p122">エクスポートする証明書のパスとファイル名を入力し、ファイル拡張子に .pfx を指定します。このパスは、プール内の他のすべてのエッジ サーバーからアクセスできるパスにするか、USB フラッシュ ドライブなどリムーバブル メディアを使用して転送可能にする必要があります。[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="a6e90-243">[証明書のエクスポートウィザードの完了] ダイアログの概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="a6e90-244">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-244">Click **Finish**.</span></span>

13. <span data-ttu-id="a6e90-245">[正常なエクスポート] ダイアログで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="a6e90-246">「 [Lync Server 2013 の外部エッジインターフェイスの証明書をセットアップ](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md)する」の手順に従って、エクスポートした証明書ファイルを他のエッジサーバーにインポートします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="a6e90-247">エッジサーバーに内部証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="a6e90-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="a6e90-248">各エッジ サーバーの展開ウィザードで、**[ステップ 3:証明書の要求、インストール、または割り当て]** の横にある **[再実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="a6e90-249">**[利用可能な証明書タスク]** ページで、**[既存の証明書を割り当てる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="a6e90-250">[**証明書の割り当て**] ページで、一覧から [**エッジ内部**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="a6e90-251">[**証明書ストア**] ページで、内部エッジに対してインポートした証明書 (前の手順) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="a6e90-252">**[証明書割り当ての概要]** ページで設定を確認し、**[次へ]** をクリックして証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a6e90-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="a6e90-253">ウィザードの完了ページで **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6e90-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="a6e90-254">この手順を使用して内部エッジ証明書を割り当てると、各サーバーで証明書スナップインを開き、[**証明書 (ローカルコンピューター)**]、[**個人**]、[**証明書**] の順に展開し、[詳細] ウィンドウで内部エッジ証明書が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="a6e90-255">展開に複数のエッジ サーバーが含まれる場合は、各エッジ サーバーでこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a6e90-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

