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
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="276d7-102">Lync Server 2013 でのサーバーの証明書の構成</span><span class="sxs-lookup"><span data-stu-id="276d7-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="276d7-103">_**最終更新日:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="276d7-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="276d7-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるか、適切な権限が委任されているユーザーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="276d7-105">権限の委任の詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="276d7-106">組織によっては、証明書を要求するための要件によっては、他のグループメンバーシップが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="276d7-107">公開キー基盤 (PKI) 証明機関 (CA) を管理するグループと相談します。</span><span class="sxs-lookup"><span data-stu-id="276d7-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="276d7-108">Lync Server 2013 には、Windows 7、Windows Server 512 R2、Windows Server 2008、Windows Vista、または windows Server 2008 を実行しているクライアントからの接続のダイジェストのハッシュと署名アルゴリズムが使用されています (SHA-1 は、224、256、384、またはビットのダイジェストの長さを使用します)。Lync Phone Edition に加えて、Windows XP オペレーティングシステム。</span><span class="sxs-lookup"><span data-stu-id="276d7-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="276d7-109">SHA-2 スイートを使用する外部アクセスをサポートするには、同じビット長のダイジェストを使用する証明書も発行できるパブリック CA が外部証明書を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="276d7-110">ハッシュ ダイジェストや署名アルゴリズムを選択するには、証明書を使用するクライアントやサーバー、そのクライアントやサーバーが通信するその他のコンピューターやデバイスに関する理解のほか、証明書で使用されるアルゴリズムの使用方法も把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="276d7-111">オペレーティングシステムと一部のクライアントアプリケーションでサポートされているダイジェストの長さについ<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>ては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="276d7-112">各標準エディションサーバーまたはフロントエンドサーバーには、oAuthTokenIssuer 証明書、既定の証明書、web 内部証明書、web 外部証明書の4つの証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="276d7-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="276d7-113">ただし、適切なサブジェクト代替名エントリと oAuthTokenIssuer 証明書の1つの既定の証明書を要求して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="276d7-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="276d7-114">証明書の要件の詳細については、「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="276d7-115">OAuthTokenIssuer 証明書の要求、割り当て、インストールの詳細については、「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="276d7-116">Standard Edition server またはフロントエンドサーバー証明書を要求、割り当て、インストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="276d7-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="276d7-117">各フロントエンドサーバーに対して手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="276d7-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="276d7-118">次の手順では、組織によって展開された、またはオフライン要求処理を使用して、社内のエンタープライズ PKI から証明書を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="276d7-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="276d7-119">パブリック CA から証明書を取得する方法については、計画ドキュメントの「 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 の内部サーバーの証明書要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="276d7-120">また、この手順では、フロントエンドサーバーのセットアップ時に証明書を要求、割り当て、インストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="276d7-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="276d7-121">事前に証明書を要求している場合は、この展開ドキュメントの「 <A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 について事前に証明書を要求する (オプション)</A> 」で説明している手順を実行します。または、組織内に展開された社内のエンタープライズ PKI を使って証明書を取得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="276d7-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="276d7-122">フロントエンドサーバー用の証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="276d7-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="276d7-123">Lync Server 展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**を行う] の横にある [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="276d7-124">**証明書ウィザード**のページで [**要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="276d7-125">[**証明書の要求**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="276d7-p107">[**要求を後で送信または今すぐ送信**] ページで、[**次へ**] をクリックすることで、既定の [**要求をすぐにオンライン証明機関に送信する**] オプションを承諾できます。このオプションを選択した場合、自動オンライン登録による内部 CA を利用可能にする必要があります。要求延期オプションを選択すると、証明書の要求ファイルを保存するための名前と場所の入力を求められます。証明書の要求は、組織内の CA またはパブリック CA へ送信され、そこで処理される必要があります。要求者は証明書応答をインポートして、適切な証明書の役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="276d7-131">[**証明機関 (CA) の選択**] ページで、[**環境内で検出されたリストから ca を選択**する] オプションを選び、一覧から [Active Directory ドメインサービス (Active DIRECTORY Domain Services) ca への登録] を選びます。</span><span class="sxs-lookup"><span data-stu-id="276d7-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="276d7-132">または [**別の証明機関を指定してください**] をクリックして、ボックスに別の CA の名前を入力してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="276d7-133">[**証明機関のアカウント**] ページで、CA に対する証明書要求の要求および処理のために、資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="276d7-133">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA.</span></span> <span data-ttu-id="276d7-134">証明書を要求するためには、ユーザー名とパスワードが必要かどうかを、事前に判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-134">You should have determined if a user name and password is necessary to request a certificate in advance.</span></span> <span data-ttu-id="276d7-135">CA 管理者には、必要な情報が含まれているため、この手順についてサポートが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-135">Your CA administrator will have the required information and may have to assist you in this step.</span></span> <span data-ttu-id="276d7-136">別の資格情報の入力が必要な場合は、チェック ボックスをオンにして、テキスト ボックスにユーザー名とパスワードを入力してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-136">If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="276d7-137">[**代替証明書テンプレートの指定**] ページで、既定の Web サーバー テンプレートを使用する場合は [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="276d7-p110">CA の既定の Web サーバー テンプレートの代わりに使用するテンプレートを組織が作成している場合は、チェック ボックスをオンにして、代替テンプレートの名前を入力します。CA 管理者が定義したテンプレートの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="276d7-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="276d7-140">[**名前とセキュリティの設定**] ページで、証明書と目的を識別できる**フレンドリ名**を指定します。</span><span class="sxs-lookup"><span data-stu-id="276d7-140">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose.</span></span> <span data-ttu-id="276d7-141">空白のままにした場合、名前は自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="276d7-141">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="276d7-142">キーの [**ビット長**] を設定するか、既定の 2048 ビットをそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="276d7-142">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="276d7-143">証明書と秘密キーを別のシステムに移動またはコピーする必要があると判断した場合は、[**証明書の秘密キーをエクスポート可能としてマークする**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-143">Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="276d7-144">Lync Server 2013 は、エクスポート可能な秘密キーの要件を最小限に抑えています。</span><span class="sxs-lookup"><span data-stu-id="276d7-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="276d7-145">その対象の 1 つがプール内のエッジ サーバーで、ここではメディア リレー認証サービスが、プール内の各インスタンスに対する個々の証明書ではなく、証明書のコピーを使用します。</span><span class="sxs-lookup"><span data-stu-id="276d7-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="276d7-146">[**組織情報**] ページで、必要に応じて組織情報を入力してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="276d7-147">[**地理情報**] ページで、必要に応じて地理情報を入力してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="276d7-148">[**サブジェクト名/サブジェクト代替名**] ページで、追加するサブジェクトの別名を確認してから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="276d7-149">[**SIP ドメインの設定**] ページで、[**SIP ドメイン**] をクリックしてから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="276d7-150">[**追加のサブジェクト代替名の構成**] ページで、追加する必須サブジェクトの別名 (今後追加する SIP ドメインで必要になる可能性がある名前を含む) を入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="276d7-p113">[**証明書要求の概要**] ページで、概要情報を確認します。情報が正しい場合には、[**次へ**] をクリックします。設定を修正または変更する必要がある場合には、[**戻る**] をクリックして、該当するページで修正または変更します。</span><span class="sxs-lookup"><span data-stu-id="276d7-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="276d7-154">[**コマンドを実行しています**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="276d7-155">On the **Online Certificate Request Status** page, review the information returned.</span><span class="sxs-lookup"><span data-stu-id="276d7-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="276d7-156">You should note that the certificate was issued and installed into the local certificate store.</span><span class="sxs-lookup"><span data-stu-id="276d7-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="276d7-157">発行およびインストールされているが有効ではないと報告される場合は、CA ルート証明書がサーバーの信頼済みルート CA ストアにインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="276d7-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span><span class="sxs-lookup"><span data-stu-id="276d7-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="276d7-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span><span class="sxs-lookup"><span data-stu-id="276d7-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="276d7-160">既定では、[**証明書を Lync Server 証明書の使用に割り当てる**] チェックボックスはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="276d7-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="276d7-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="276d7-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="276d7-162">前のページで [**証明書を Lync Server 証明書の使用状況に割り当てる**] チェックボックスをオフにした場合は、[**証明書の割り当て**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="276d7-162">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="276d7-163">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="276d7-163">Click **Next**.</span></span>

18. <span data-ttu-id="276d7-p116">[**証明書ストア**] ページで、要求した証明書を選択します。証明書を表示するには、[**証明書の詳細の表示**] をクリックし、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="276d7-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="276d7-166">[<STRONG>オンライン証明</STRONG>書の要求の状態] ページで証明書の問題 (証明書が有効ではないなど) が報告された場合は、実際の証明書を表示すると、問題の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="276d7-166">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue.</span></span> <span data-ttu-id="276d7-167">証明書が無効になる原因となる可能性のある特定の問題は、前に説明した信頼されていないルート CA 証明書と、証明書に関連付けられている秘密キーが見つからないことです。</span><span class="sxs-lookup"><span data-stu-id="276d7-167">Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate.</span></span> <span data-ttu-id="276d7-168">この2つの問題を解決するには、CA のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="276d7-168">Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="276d7-169">[**証明書の割り当ての概要**] ページに表示された情報から、適切な証明書が割り当てられていることを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="276d7-p118">[**コマンドの実行**] ページで、コマンドの出力を確認します。割り当てプロセスを確認する場合、またはエラーや警告が発行されたかどうかを確認する場合には、[**ログの表示**] をクリックします。確認を終了したら、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="276d7-173">[**証明書ウィザード**] ページで、証明書の**状態**が [割り当て済み] であることを確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="276d7-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="276d7-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="276d7-174">See Also</span></span>


[<span data-ttu-id="276d7-175">Lync Server 2013 の証明書インフラストラクチャの要件</span><span class="sxs-lookup"><span data-stu-id="276d7-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

