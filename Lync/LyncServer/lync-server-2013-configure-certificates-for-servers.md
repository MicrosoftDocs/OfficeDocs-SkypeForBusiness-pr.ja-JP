---
title: 'Lync Server 2013: サーバーの証明書の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d23410257db89ff0c7498aba879444a5be9707
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521064"
---
# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="0e4b0-102">Lync Server 2013 のサーバーの証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="0e4b0-102">Configure certificates for servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e4b0-103">_**トピックの最終更新日:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="0e4b0-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="0e4b0-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバー ユーザーとしてログオンするか、適切なアクセス許可が委任されているユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="0e4b0-105">アクセス許可の委任の詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="0e4b0-106">組織や証明書要求の要件によっては、他のグループ メンバーシップが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="0e4b0-107">使用する公開キー基盤 (PKI) の証明機関 (CA) を管理するグループと相談してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e4b0-108">Lync Server 2013 には、Lync Phone Edition に加えて、Windows 7、Windows Server 512 R2、Windows Server 2008、Windows Vista、または Windows XP オペレーティングシステムを実行しているクライアントからの接続に対して、SHA-1 スイートのサポートが含まれています (SHA-1 は、224、256、384、または2008ビットのダイジェストの長さを使用)。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="0e4b0-109">SHA-1 スイートを使用して外部アクセスをサポートするために、外部証明書はパブリック CA によって発行され、同じビット長のダイジェストを使用して証明書を発行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="0e4b0-110">どのハッシュダイジェストと署名アルゴリズムを選択するかは、その証明書を使用するクライアントとサーバー、およびクライアントとサーバーが通信するその他のコンピューターとデバイスが、証明書で使用されているアルゴリズムの使用方法についても知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="0e4b0-111">オペレーティングシステムと一部のクライアントアプリケーションでサポートされているダイジェストの長さについては、「」を参照してください <A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A> 。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="0e4b0-112">各 Standard Edition サーバーまたはフロントエンドサーバーは、最大4つの証明書 (oAuthTokenIssuer 証明書、既定の証明書、web 内部証明書、web 外部証明書) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="0e4b0-113">ただし、適切なサブジェクトの別名エントリおよび oAuthTokenIssuer 証明書を使用して、1つの既定の証明書を要求して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="0e4b0-114">証明書の要件の詳細については、「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="0e4b0-115">OAuthTokenIssuer 証明書の要求、割り当て、およびインストールの詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="0e4b0-116">Standard Edition サーバーまたはフロントエンドサーバーの証明書を要求、割り当て、およびインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="0e4b0-117">各フロントエンドサーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e4b0-118">次の手順では、組織によって展開され、オフライン要求処理を使用して展開された内部エンタープライズ PKI から証明書を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="0e4b0-119">パブリック CA からの証明書の取得の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 の内部サーバーの証明書要件</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="0e4b0-120">また、この手順では、フロントエンドサーバーのセットアップ時に証明書を要求、割り当て、およびインストールする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="0e4b0-121">事前に証明書を要求した場合は、この展開ドキュメントの「 <A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 の証明書を事前に要求する (オプション)</A> 」を参照してください。または、証明書を取得するために組織内に展開されている内部エンタープライズ PKI を使用していない場合は、この手順を適切に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="0e4b0-122">フロントエンドサーバーの証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="0e4b0-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="0e4b0-123">Lync Server 展開ウィザードで、[**ステップ 3: 証明書の要求、インストール、または割り当て**] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="0e4b0-124">**証明書ウィザード**のページで **[要求]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="0e4b0-125">**[証明書要求]** ページで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="0e4b0-126">[**遅延または即時要求**] ページで、[**次へ**] をクリックして、[**オンライン証明機関に直ちに要求を送信する**] オプションをそのまま使用できます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-126">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**.</span></span> <span data-ttu-id="0e4b0-127">このオプションを選択する場合は、自動オンライン登録を使用する内部 CA を使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-127">The internal CA with automatic online enrollment must be available if you select this option.</span></span> <span data-ttu-id="0e4b0-128">要求を延期するオプションを選択すると、証明書要求ファイルを保存するための名前と場所の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-128">If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file.</span></span> <span data-ttu-id="0e4b0-129">証明書要求は、組織内またはパブリック CA のどちらかで、CA によって提示および処理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-129">The certificate request must be presented and processed by a CA either inside your organization, or by a public CA.</span></span> <span data-ttu-id="0e4b0-130">その後、証明書応答をインポートして、適切な証明書の役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-130">You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="0e4b0-131">[ **証明機関 (ca) を選択** してください] ページで、[ **環境で検出されたリストから CA を選択** してください] オプションを選択し、一覧から (Active Directory ドメインサービスへの登録を通じて) ca を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="0e4b0-132">または、[ **別の証明機関を指定** する] オプションを選択し、別の CA の名前をボックスに入力して、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="0e4b0-p109">**[証明機関のアカウント]** ページで、CA に対する証明書要求の要求および処理のために、資格情報の入力を求められます。 証明書を要求するためには、ユーザー名とパスワードが必要かどうかを、事前に判断する必要があります。 必要な情報は CA 管理者が保有しているので、このステップでは CA 管理者のサポートが必要な場合もあります。 別の資格情報の入力が必要な場合は、チェック ボックスをオンにし、テキスト ボックスにユーザー名とパスワードを入力してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-p109">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and may have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="0e4b0-137">**[代替証明書テンプレートの指定]** ページで、既定の Web サーバー テンプレートを使用する場合は **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e4b0-p110">CA の既定の Web サーバー テンプレートの代わりに使用するテンプレートを組織が作成している場合は、チェック ボックスをオンにして、代替のテンプレートの名前を入力します。 CA 管理者が定義したテンプレートの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="0e4b0-140">**[名前およびセキュリティの設定]** ページで、証明書と目的を特定できる **[フレンドリ名]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="0e4b0-141">空白のままにした場合、名前は自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="0e4b0-142">キーの **[ビット長]** を設定するか、既定の 2048 ビットをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="0e4b0-143">証明書と秘密キーを他のシステムに移動またはコピーする必要があると判断した場合は、[ **証明書の秘密キーをエクスポート可能としてマーク** する] を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e4b0-144">Lync Server 2013 には、エクスポート可能な秘密キーに対する最小限の要件があります。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="0e4b0-145">その対象の 1 つがプール内のエッジ サーバーで、ここではメディア リレー認証サービスが、プール内の各インスタンスに対する個々の証明書ではなく、証明書のコピーを使用します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="0e4b0-146">[ **組織情報** ] ページで、必要に応じて組織情報を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="0e4b0-147">[ **地理情報** ] ページで、必要に応じて地理情報を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="0e4b0-148">**[サブジェクト名/サブジェクト代替名]** ページで、追加するサブジェクトの別名を確認してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="0e4b0-149">[ **Sip ドメインの設定** ] ページで、 **sip ドメイン**を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="0e4b0-150">[ **追加のサブジェクト代替名の構成** ] ページで、追加の必要なサブジェクトの別名 (今後追加する SIP ドメインに必要なものも含む) を追加し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="0e4b0-151">[ **証明書要求の概要** ] ページで、概要の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-151">On the **Certificate Request Summary** page, review the information in the summary.</span></span> <span data-ttu-id="0e4b0-152">情報が正しい場合は、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-152">If the information is correct, click **Next**.</span></span> <span data-ttu-id="0e4b0-153">設定を修正または変更する必要がある場合は、適切なページに **戻る** をクリックして修正または修正を行います。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-153">If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="0e4b0-154">**[コマンドを実行しています]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="0e4b0-155">[ **オンライン証明書要求の状態** ] ページで、返された情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="0e4b0-156">証明書が発行され、ローカル証明書ストアにインストールされていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="0e4b0-157">発行済みとインストール済みであるが、有効ではないと報告された場合は、CA ルート証明書がサーバーの信頼されたルート CA ストアにインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="0e4b0-158">信頼されたルート CA 証明書を取得する方法については、CA のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="0e4b0-159">取得した証明書を表示する必要がある場合は、[ **証明書の詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="0e4b0-160">既定では、[ **Lync Server 証明書の使用法に証明書を割り当てる** ] チェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="0e4b0-161">証明書を手動で割り当てる場合は、このチェックボックスをオフにして、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="0e4b0-162">前のページの「 **証明書を Lync Server 証明書の使用法に割り当てる** 」チェックボックスをオフにした場合は、[ **証明書の割り当て** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="0e4b0-163">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-163">Click **Next**.</span></span>

18. <span data-ttu-id="0e4b0-164">[ **証明書ストア** ] ページで、要求した証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-164">On the **Certificate Store** page, select the certificate that you requested.</span></span> <span data-ttu-id="0e4b0-165">証明書を表示する場合は、[ **証明書の詳細の表示**] をクリックし、[ **次** へ] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-165">If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0e4b0-166">[ <STRONG>オンライン証明書要求の状態</STRONG> ] ページで証明書に関する問題 (証明書が有効でないなど) が報告された場合は、実際の証明書を表示することで問題解決に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="0e4b0-167">証明書が有効でない原因となる2つの特定の問題として、既に説明した信頼できるルート CA 証明書と、証明書に関連付けられている秘密キーが見つからないことが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="0e4b0-168">これら2つの問題を解決するには、CA のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="0e4b0-169">[ **証明書の割り当ての概要** ] ページで、提示された情報を確認して、割り当てられる証明書であることを確認してから、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="0e4b0-170">[ **コマンドの実行** ] ページで、コマンドの出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-170">On the **Executing Commands** page, review the output of the command.</span></span> <span data-ttu-id="0e4b0-171">割り当てプロセスを確認する場合、またはエラーまたは警告が発行された場合は、[ **ログの表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-171">Click **View Log** if you want to review the assignment process or if there was an error or warning issued.</span></span> <span data-ttu-id="0e4b0-172">レビューが終了したら、[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-172">When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="0e4b0-173">[ **証明書ウィザード** ] ページで、証明書の **状態** が "割り当て済み" であることを確認し、[ **閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e4b0-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e4b0-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e4b0-174">See Also</span></span>


[<span data-ttu-id="0e4b0-175">Lync Server 2013 の証明書インフラストラクチャ要件</span><span class="sxs-lookup"><span data-stu-id="0e4b0-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

