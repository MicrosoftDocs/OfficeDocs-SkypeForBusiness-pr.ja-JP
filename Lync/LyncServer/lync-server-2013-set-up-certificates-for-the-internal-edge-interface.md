---
title: 'Lync Server 2013: 内部エッジ インターフェイス用の証明書の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53ba11db5d2c9fc727b7720a1a10d5da547075c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="6d132-102">Lync Server 2013 での内部エッジ インターフェイス用の証明書の設定</span><span class="sxs-lookup"><span data-stu-id="6d132-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d132-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6d132-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6d132-104">証明書ウィザードを実行するときは、使用する証明書テンプレートの種類に対して適切な権限が割り当てられているグループのメンバーであるアカウントを使用してログインしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d132-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="6d132-105">既定では、Lync Server 2013 証明書の要求では、Web サーバー証明書テンプレートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6d132-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="6d132-106">RTCUniversalServerAdmins グループのメンバーであるアカウントを使用して、このテンプレートを使用して証明書を要求する場合は、そのテンプレートを使用するために必要な登録権限がグループに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d132-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="6d132-107">各エッジサーバーの内部インターフェイスには1つの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="6d132-107">A single certificate is required on the internal interface of each Edge Server.</span></span> <span data-ttu-id="6d132-108">内部インターフェイスの証明書は、社内のエンタープライズ証明機関 (CA) またはパブリック CA によって発行できます。</span><span class="sxs-lookup"><span data-stu-id="6d132-108">Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA.</span></span> <span data-ttu-id="6d132-109">組織で内部 CA が展開されている場合は、内部 CA を使って内部インターフェイスの証明書を発行することによって、公開証明書を使用する経費を節約できます。</span><span class="sxs-lookup"><span data-stu-id="6d132-109">If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface.</span></span> <span data-ttu-id="6d132-110">内部の Windows Server 2008 CA または Windows Server 2008 R2 CA を使って、これらの証明書を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d132-110">You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="6d132-111">このような証明書の要件の詳細については、「 [Lync Server 2013 の外部ユーザーアクセスの証明書の要件](lync-server-2013-certificate-requirements-for-external-user-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d132-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="6d132-112">サイトで内部エッジインターフェイスで証明書を設定するには、このセクションの手順を使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d132-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="6d132-113">各エッジサーバーに、内部インターフェイス用の CA 認定チェーンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6d132-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="6d132-114">各エッジサーバー上で、内部インターフェイスの CA 認定チェーンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d132-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="6d132-115">1台のエッジサーバー上で、最初のエッジサーバーと呼ばれる内部インターフェイスの証明書要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d132-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="6d132-116">第1エッジサーバー上の内部インターフェイスの証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d132-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="6d132-117">このサイトの他のエッジサーバー (またはこのロードバランサーの背後に展開されたもの) に証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d132-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="6d132-118">各エッジサーバーの内部インターフェイス用の証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6d132-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="6d132-119">エッジサーバー (複数サイトエッジトポロジ) を持つ複数のサイトがある場合、または別のロードバランサーの背後に展開されているエッジサーバーのセットを個別に使用している場合は、エッジサーバーを持つサイトとエッジサーバーのセットごとに、次の手順に従う必要があります。別のロードバランサーの背後に展開されます。</span><span class="sxs-lookup"><span data-stu-id="6d132-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d132-120">このセクションの手順は、Windows Server&nbsp;2008 Ca、windows server&nbsp;2008&nbsp;R2 ca、windows Server 2012 CA、または windows server 2012 R2 Ca を使用して、エッジサーバーごとに証明書を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d132-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="6d132-121">その他の CA のステップバイステップガイドについては、その CA のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d132-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="6d132-122">既定では、認証されたすべてのユーザーは、証明書を要求するための適切なユーザー権利を持っています。</span><span class="sxs-lookup"><span data-stu-id="6d132-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="6d132-123">このセクションの手順は、エッジサーバー展開プロセスの一部としてエッジサーバー上で証明書要求を作成することに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6d132-123">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process.</span></span> <span data-ttu-id="6d132-124">フロントエンドサーバーを使用して証明書要求を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d132-124">It is possible to create certificate requests using the Front End Server.</span></span> <span data-ttu-id="6d132-125">この操作を行うと、エッジサーバーの展開を開始する前に、計画および展開プロセスの早い段階で証明書の要求を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="6d132-125">You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers.</span></span> <span data-ttu-id="6d132-126">これを行うには、要求する証明書が、エクスポート可能な秘密キーを使って定義されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d132-126">To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="6d132-127">このセクションの手順では、証明書の .cer ファイルと. p7b ファイルの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d132-127">The procedures in this section describe using a .cer and a .p7b file for the certificate.</span></span> <span data-ttu-id="6d132-128">別の種類のファイルを使用する場合は、必要に応じて次の手順を変更します。</span><span class="sxs-lookup"><span data-stu-id="6d132-128">If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="6d132-129">Certsrv Web サイトを使用して内部インターフェイスの CA 証明チェーンをダウンロードするには</span><span class="sxs-lookup"><span data-stu-id="6d132-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="6d132-130">内部ネットワーク (エッジサーバーではなく) の Lync Server 2013 サーバーに、**管理者**グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d132-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="6d132-131">[**スタート**] ボタンをクリックし、[**実行**] をクリックして、次のように入力して、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6d132-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="6d132-132">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6d132-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d132-133">Windows Server 2008 または Windows Server 2008 R2 enterprise CA を使用している場合は、http ではなく https を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d132-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="6d132-134">発行元の CA の certsrv Web ページで、[**タスクの選択**] の [**CA 証明書、証明書チェーン、または CRL のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="6d132-135">**Ca 証明書、証明書チェーン、または CRL をダウンロードする**には、[ **ca 証明書チェーンのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="6d132-136">[**ファイルのダウンロード**] ダイアログボックスで、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="6d132-137">サーバー上のハードディスクドライブに. p7b ファイルを保存して、各エッジサーバー上のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6d132-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d132-138">. P7b ファイルには、証明パス内のすべての証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6d132-138">The .p7b file contains all of the certificates that are in the certification path.</span></span> <span data-ttu-id="6d132-139">証明のパスを表示するには、サーバー証明書を開き、証明のパスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-139">To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="6d132-140">MMC を使用して内部インターフェイスの CA 証明チェーンをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="6d132-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="6d132-141">Microsoft 管理コンソール (MMC) を使って、任意のドメインに参加しているコンピューターから CA ルート証明書をエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d132-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="6d132-142">[**スタート**] をクリックし、[**実行**] をクリックして、「 **MMC**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6d132-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="6d132-143">MMC コンソールで、[**ファイル**] をクリックし、[**追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="6d132-144">[スナップインの**追加または削除**] ダイアログボックスで、[**証明書**] を選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-144">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**.</span></span> <span data-ttu-id="6d132-145">メッセージが表示されたら、[**コンピューターアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-145">When prompted, select **Computer Account**.</span></span> <span data-ttu-id="6d132-146">[**コンピューターの選択**] ダイアログで、[**ローカル コンピューター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-146">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="6d132-147">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-147">Click **Finish**.</span></span> <span data-ttu-id="6d132-148">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-148">Click **OK**.</span></span>

4.  <span data-ttu-id="6d132-149">[**証明書 (ローカルコンピューター)**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="6d132-149">Expand **Certificates (Local Computer)**.</span></span> <span data-ttu-id="6d132-150">[**信頼されたルート証明機関**] を展開し、[**証明書**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-150">Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="6d132-151">使用している CA によって発行されたルート証明書をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-151">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="6d132-152">証明書を右クリックし、[**すべてのタスク**] を選択して、[**エクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-152">Right click the certificate, select **All Tasks**, select **Export**.</span></span> <span data-ttu-id="6d132-153">**証明書のエクスポートウィザード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="6d132-153">The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="6d132-154">**証明書のエクスポート ウィザード**で、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="6d132-155">[**エクスポートファイルの形式**] ダイアログボックスで、エクスポート先の形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="6d132-156">**暗号化メッセージ構文標準– PKCS \#7 証明書 () をお勧めします。P7B)**。</span><span class="sxs-lookup"><span data-stu-id="6d132-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="6d132-157">**暗号化メッセージ構文標準– PKCS \#7 証明書 (.P7B)** で、[証明の**パスにすべての証明書を含める**] チェックボックスをオンにして、ルート ca 証明書や中間 CA 証明書などの証明書チェーンをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6d132-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="6d132-158">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-158">Click **Next**.</span></span>

8.  <span data-ttu-id="6d132-159">[**エクスポートするファイル**] ダイアログボックスの [ファイル名] エントリに、エクスポートされた証明書のパスとファイル名 (既定の拡張子は. p7b) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d132-159">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate.</span></span> <span data-ttu-id="6d132-160">必要に応じて [**参照**] をクリックし、エクスポートされた証明書を配置するディレクトリを見つけて、エクスポートされた証明書の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d132-160">Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate.</span></span> <span data-ttu-id="6d132-161">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-161">Click **Save**.</span></span> <span data-ttu-id="6d132-162">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-162">Click **Next**.</span></span>

9.  <span data-ttu-id="6d132-163">操作の概要を確認し、[**完了**] をクリックして、証明書のエクスポートを完了します。</span><span class="sxs-lookup"><span data-stu-id="6d132-163">Review the summary of actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="6d132-164">エクスポートが正常に完了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-164">Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="6d132-165">内部インターフェイスの CA 証明チェーンをインポートするには</span><span class="sxs-lookup"><span data-stu-id="6d132-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="6d132-166">各エッジサーバーで、[**スタート**] をクリックし、[**実行**] をクリックして、[**開く**] ボックスに「 **MMC** 」と入力し、[ **OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。</span><span class="sxs-lookup"><span data-stu-id="6d132-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="6d132-167">[**ファイル**] メニューで、[スナップインの**追加と削除**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="6d132-168">[**スタンドアロンスナップ**インの追加] ボックスで、[**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="6d132-169">[**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="6d132-170">**[コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター (このコンソールが実行されているコンピューター)** ] チェックボックスがオンになっていることを確認して、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="6d132-171">[**閉じる**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="6d132-172">コンソールツリーで、[**証明書 (ローカルコンピューター)**] を展開し、[**信頼されたルート証明機関**] を右クリックし、[**すべてのタスク**] をポイントして、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="6d132-173">ウィザードの [**インポートするファイル**] で、証明書のファイル名を指定します (これは、前の手順で、内部インターフェイスの CA 認定チェーンをダウンロードしたときに指定した名前です)。</span><span class="sxs-lookup"><span data-stu-id="6d132-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="6d132-174">各エッジサーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6d132-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="6d132-175">内部インターフェイスの証明書の要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="6d132-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="6d132-176">エッジサーバーのいずれかで、展開ウィザードを開始し、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d132-177">プール内の1つの場所に複数のエッジサーバーがある場合は、いずれかのエッジサーバーで証明書ウィザードを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="6d132-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="6d132-178">手順3を初めて実行した後は、ボタンが<STRONG>もう一度実行</STRONG>され、すべての証明書が要求、インストール、割り当てられるまで、タスクが正常に完了したことを示す緑色のチェックマークが表示されません。</span><span class="sxs-lookup"><span data-stu-id="6d132-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="6d132-179">[**利用可能な証明書タスク**] ページで、[**新しい証明書要求を作成する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="6d132-180">[**証明書の要求**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="6d132-181">[**要求を後で送信または今すぐ送信**] ページで、[**要求を準備して後で送信する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="6d132-182">[**証明書の要求ファイル**] ページで、要求の保存先の完全なパスとファイル名を入力します (たとえば、 **c\_:\_\\cert の内部エッジ. .cer**)。</span><span class="sxs-lookup"><span data-stu-id="6d132-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="6d132-183">[**代替証明書テンプレートの指定**] ページで、既定の web サーバテンプレート以外のテンプレートを使用するには、[**選択した証明機関に別の証明書テンプレートを使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6d132-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="6d132-184">[**名前とセキュリティの設定**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d132-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="6d132-185">[**フレンドリ名**] に、証明書の表示名 (内部エッジなど) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d132-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="6d132-186">**ビット長**では、ビット長 (通常は**2048**の既定値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d132-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="6d132-187">ビット長を高くするとセキュリティが向上しますが、速度に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d132-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="6d132-188">証明書をエクスポート可能にする必要がある場合は、[**証明書の秘密キーをエクスポート可能としてマーク**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="6d132-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="6d132-189">[**組織の情報**] ページで、組織の名前と組織単位 (OU) を入力します (たとえば、部門または部門)。</span><span class="sxs-lookup"><span data-stu-id="6d132-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="6d132-190">[**地理情報**] ページで、場所情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d132-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="6d132-191">[ **Subject Name/Subject name** ] ページには、ウィザードによって自動的に入力される情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d132-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="6d132-192">[**追加のサブジェクト代替名の構成**] ページで、必要なその他のサブジェクトの代替名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d132-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="6d132-193">[**要求の概要**] ページで、要求を生成するために使用される証明書情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d132-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="6d132-194">コマンドが完了したら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d132-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="6d132-195">証明書要求のログを表示するには、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="6d132-196">証明書の要求を完了するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="6d132-197">[**証明書要求ファイル**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6d132-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="6d132-198">生成された証明書署名要求 (CSR) ファイルを表示するには、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="6d132-199">ウィザードを閉じるには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="6d132-200">このファイルを CA (企業の組織でサポートされているメールまたはその他の方法で) に送信し、応答ファイルを受信したら、新しい証明書をこのコンピューターにコピーして、インポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="6d132-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="6d132-201">内部インターフェイスの証明書をインポートするには</span><span class="sxs-lookup"><span data-stu-id="6d132-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="6d132-202">ローカル管理者グループのメンバーとして証明書要求を作成したエッジサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d132-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="6d132-203">展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="6d132-204">手順3を初めて実行した後は、ボタンが**もう一度実行**されますが、必須の証明書が要求、インストール、割り当てられるまで緑のチェックマークは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6d132-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="6d132-205">[**利用可能な証明書タスク**] ページで、[ **a から証明書をインポートする] をクリックします。P7b、.pfx、.cer のいずれかのファイル**。</span><span class="sxs-lookup"><span data-stu-id="6d132-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="6d132-206">[**証明書のインポート**] ページで、このエッジサーバーの内部インターフェイスに対して要求された証明書の完全パスとファイル名を入力します (または、[**参照**] をクリックして、ファイルを見つけて選択します)。</span><span class="sxs-lookup"><span data-stu-id="6d132-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="6d132-207">プールの他のメンバーの証明書をインポートする場合は、秘密キーを含む証明書を [**証明書ファイルを含む**] チェックボックスをオンにして、パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d132-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="6d132-208">プール内のエッジサーバーの秘密キーを使って証明書をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="6d132-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="6d132-209">証明書をインポートしたのと同じエッジサーバーに、管理者グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6d132-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="6d132-210">[**スタート**] をクリックし、[**実行**] をクリックして、「 **MMC**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6d132-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="6d132-211">MMC コンソールで、[**ファイル**] をクリックし、[**スナップインの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="6d132-212">[スナップインの追加または削除] ページで、[**証明書**] をクリックし、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="6d132-213">[証明書] スナップインダイアログボックスで、[**コンピューターアカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-213">In the Certificates snap-in dialog, select **Computer account**.</span></span> <span data-ttu-id="6d132-214">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-214">Click **Next**.</span></span> <span data-ttu-id="6d132-215">[コンピューターの選択] で、[**ローカルコンピューター] (このコンソールが実行されているコンピューター)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-215">In Select Computer, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="6d132-216">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-216">Click **Finish**.</span></span> <span data-ttu-id="6d132-217">[ **OK** ] をクリックして、MMC コンソールの構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="6d132-217">Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="6d132-218">[**証明書 (ローカルコンピューター)** ] をダブルクリックして、証明書ストアを展開します。</span><span class="sxs-lookup"><span data-stu-id="6d132-218">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="6d132-219">[**個人用**] をダブルクリックし、[**証明書**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-219">Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6d132-220">ローカルコンピューターの証明書の個人用ストアに証明書がない場合は、インポートされた証明書に関連付けられた秘密キーがありません。</span><span class="sxs-lookup"><span data-stu-id="6d132-220">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="6d132-221">要求とインポートの手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d132-221">Review the request and import steps.</span></span> <span data-ttu-id="6d132-222">問題が解決しない場合は、証明機関の管理者またはプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6d132-222">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="6d132-223">ローカルコンピューターの証明書の個人用ストアで、エクスポートする証明書を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-223">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting.</span></span> <span data-ttu-id="6d132-224">[**すべてのタスク**] をクリックし、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-224">Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="6d132-225">証明書のエクスポートウィザードで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-225">In the Certificate Export Wizard, click **Next**.</span></span> <span data-ttu-id="6d132-226">[**はい、秘密キーをエクスポートします**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-226">Select **Yes, export the private key**.</span></span> <span data-ttu-id="6d132-227">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-227">Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d132-228"><STRONG>[はい、秘密キーをエクスポート</STRONG>します] を選択できない場合は、この証明書に関連付けられている秘密キーがエクスポート対象としてマークされていません。</span><span class="sxs-lookup"><span data-stu-id="6d132-228">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="6d132-229">エクスポートを続行する前に、証明書が秘密キーのエクスポートを許可するようにマークされていることを確認して、証明書をもう一度要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d132-229">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="6d132-230">証明機関の管理者またはプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="6d132-230">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="6d132-231">[エクスポートファイルの形式] ダイアログボックスで、[ **Personal Information\#Exchange – PKCS 12 ()] を選びます。PFX)** を選び、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="6d132-232">可能であれば証明のパスにすべての証明書を含める</span><span class="sxs-lookup"><span data-stu-id="6d132-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="6d132-233">すべての拡張プロパティをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="6d132-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="6d132-234">エッジサーバーから証明書をエクスポートするときに、<STRONG>エクスポートが正常に完了した場合は、[秘密キーの削除</STRONG>] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="6d132-234">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="6d132-235">このオプションを選択すると、証明書と秘密キーをこのエッジサーバーにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d132-235">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="6d132-236">[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="6d132-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="6d132-237">秘密キーを保護するためにパスワードを割り当てる場合は、秘密キーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6d132-237">If you want to assign password to protect the private key, type a password for the private key.</span></span> <span data-ttu-id="6d132-238">確認のためにパスワードを再入力します。</span><span class="sxs-lookup"><span data-stu-id="6d132-238">Re-enter the password to confirm.</span></span> <span data-ttu-id="6d132-239">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-239">Click **Next**.</span></span>

11. <span data-ttu-id="6d132-240">エクスポートする証明書のパスとファイル名を入力し、ファイル拡張子に .pfx を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d132-240">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="6d132-241">パスは、プール内の他のすべてのエッジサーバーからアクセス可能であるか、またはリムーバブルメディア (USB フラッシュドライブなど) を使用して転送できるものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d132-241">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="6d132-242">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-242">Click **Next**.</span></span>

12. <span data-ttu-id="6d132-243">[証明書のエクスポートウィザードを完了します] ダイアログボックスの概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d132-243">Review the summary on the Completing the Certificate Export Wizard dialog.</span></span> <span data-ttu-id="6d132-244">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-244">Click **Finish**.</span></span>

13. <span data-ttu-id="6d132-245">エクスポートの成功を示すダイアログ ボックスが表示されたら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="6d132-246">「 [Lync 2013 Server の外部エッジインターフェイスの証明書を設定](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md)する」の手順に従って、エクスポートされた証明書ファイルを他のエッジサーバーにインポートします。</span><span class="sxs-lookup"><span data-stu-id="6d132-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="6d132-247">エッジサーバーで内部証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6d132-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="6d132-248">各エッジサーバーの展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**] の横にある [実行] を**もう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="6d132-249">[**利用可能な証明書タスク**] ページで、[**既存の証明書を割り当てる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="6d132-250">[**証明書の割り当て**] ページで、一覧から [**エッジ内部**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6d132-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="6d132-251">[**証明書ストア**] ページで、(前の手順で) 内部境界にインポートした証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="6d132-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="6d132-252">[**証明書の割り当ての概要**] ページで、設定を確認し、[**次へ**] をクリックして証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6d132-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="6d132-253">ウィザードの完了ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6d132-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="6d132-254">この手順を使用して内部エッジ証明書を割り当てると、各サーバーで証明書スナップインを開き、[**証明書 (ローカルコンピューター)**]、[**個人用**]、[**証明書**] の順に展開して、[詳細] ウィンドウで確認します。内部エッジ証明書が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d132-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="6d132-255">展開に複数のエッジサーバーが含まれている場合は、各エッジサーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="6d132-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

