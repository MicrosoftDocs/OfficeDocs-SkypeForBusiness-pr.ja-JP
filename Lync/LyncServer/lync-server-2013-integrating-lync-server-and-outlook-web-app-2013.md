---
title: 'Lync Server 2013: Lync Server と Outlook Web App 2013 の統合'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="4308e-102">Microsoft Lync Server 2013 と Microsoft Outlook Web App 2013 の統合</span><span class="sxs-lookup"><span data-stu-id="4308e-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4308e-103">_**最終更新日:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="4308e-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="4308e-104">Microsoft Outlook 2013 との統合に加えて、microsoft Lync Server 2013 は microsoft Outlook Web App 2013 と完全に統合することができます。この操作を行うと、Outlook Web App にインスタントメッセージとプレゼンスが追加され、Outlook Web App と Microsoft Lync 2013 の間でユニファイド連絡先リストを共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4308e-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="4308e-105">Lync Server 2013 と Outlook Web App を統合するには、まずユニファイドコミュニケーションマネージ API 4.0 ランタイムが Microsoft Exchange Server 2013 バックエンドサーバーにインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="4308e-106">この操作を行うには、次のレジストリ値が存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4308e-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="4308e-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="4308e-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="4308e-108">ImplementationDLLPath は、Microsoft.Rtc.Internal.Ucweb.dll ファイルのフォルダーの場所をポイントします。</span><span class="sxs-lookup"><span data-stu-id="4308e-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="4308e-109">見つからない場合、またはレジストリ値が存在しない場合は、Microsoft ダウンロードセンターから、UCMA ランタイムセットアッププログラムをダウンロードしてインストールする必要<http://www.microsoft.com/en-us/download/details.aspx?id=34992>があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <http://www.microsoft.com/en-us/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="4308e-110">UCMA Runtime のインストール方法についても、この Web ページに記載されています。</span><span class="sxs-lookup"><span data-stu-id="4308e-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="4308e-111">**下位互換性**</span><span class="sxs-lookup"><span data-stu-id="4308e-111">**Backward Compatibility**</span></span>

<span data-ttu-id="4308e-112">Lync Server 2013 は、Microsoft Exchange Server 2010 バージョンのユニファイドメッセージングと Outlook Web App に統合できます。</span><span class="sxs-lookup"><span data-stu-id="4308e-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="4308e-113">詳細については、「オンプレミスの Exchange UM を展開して Lync Server 2010 ボイス[http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)メールを提供する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4308e-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="4308e-114">Exchange 2010 と統合する場合、統合連絡先ストアや Lync 間アーカイブなどの Lync Server 固有の機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="4308e-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="4308e-115">Microsoft Lync 2013 は、Exchange 2010 および Outlook 2010 と組み合わせて使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4308e-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="4308e-116">ただし、統合連絡先ストアや高解像度写真などの新機能は、Lync 2013 ユーザーには利用できません。</span><span class="sxs-lookup"><span data-stu-id="4308e-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="4308e-117">これらの新しい機能には、Lync Server 2013 と Exchange 2013 の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="4308e-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="4308e-118">**Outlook Web App 用の信頼済みアプリケーション プールを作成する**</span><span class="sxs-lookup"><span data-stu-id="4308e-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="4308e-119">Microsoft Exchange ユニファイドメッセージングコールルータサービスと Microsoft Exchange ユニファイドメッセージングサービスを同じコンピューターにインストールしている場合、Outlook Web App 用の信頼されたアプリケーションプールを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4308e-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="4308e-120">(これは、問題のサーバーが SipName UM ダイヤルプランをホストしていることを前提としています)。これらの両方のサービスをホストするために単一のコンピューターを使用している場合は、このドキュメントの「 **Outlook Web App でインスタントメッセージングを有効**にする」のセクションに進んでください。</span><span class="sxs-lookup"><span data-stu-id="4308e-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="4308e-121">Lync Server 2013 は、SipName UM ダイヤルプランをホストしているすべての Exchange サーバーを自動検出できます。これらのサーバーは、Lync Server の [既知のサーバー] リストに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="4308e-122">信頼されたアプリケーションプールを作成し、これらのサーバーを [既知のサーバー] リストに追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4308e-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="4308e-123">実際には、Outlook Web App の統合が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="4308e-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4308e-124">これは、Lync Server トポロジで、autodiscovered エントリと手動で追加されたエントリの2つのエントリが同じコンピューターに設定されていることが原因です。</span><span class="sxs-lookup"><span data-stu-id="4308e-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="4308e-125">この問題を修正し、Outlook Web App を再度動作させるには、Windows PowerShell を使用して、そのサーバーの信頼済みプールと信頼済みアプリケーションのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="4308e-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="4308e-126">詳細については、<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> および <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4308e-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="4308e-127">これら2つのサービスが別々のコンピューターで実行されている場合は、ユニファイドコミュニケーションのマネージ API 4.0 ランタイムがインストールされていることを確認した後、Lync Server の信頼済みアプリケーションプールと、それに関連付けられた信頼済みアプリケーションを作成する必要があります。Outlook Web Appこれにより、サーバーが既知のサーバーの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="4308e-128">そのためには、まず、Lync Server 管理シェルで次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4308e-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="4308e-129">上記のコマンドでは、atl-owa-001.litwareinc.com は Outlook Web App pool の完全修飾ドメイン名です。これは、Outlook Web App へのアクセスを提供する証明書のサブジェクト名とサブジェクト代替名 (SAN) フィールドに表示される名前と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="4308e-130">同様に、atl-cs-001.litwareinc.com は、新しい信頼されたアプリケーションプールをホストする Lync Server 2013 プールの完全修飾ドメイン名です。</span><span class="sxs-lookup"><span data-stu-id="4308e-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="4308e-131">また、指定したサイト Redmond が、Lync Server サイトの SiteID を表していることにも注目してください。</span><span class="sxs-lookup"><span data-stu-id="4308e-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="4308e-132">SiteID は、サイトの DisplayName と同じであるとは限りません。lync server の管理シェルから次のコマンドを実行して、Lync Server サイトの SiteIDs を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4308e-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="4308e-133">信頼済みアプリケーション プールを作成したら、次のようなコマンドを使用して、Outlook Web App のアプリケーション ID とポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="4308e-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="4308e-p110">前のコマンドで、ApplicationID は信頼済みアプリケーションを区別するために使用するわかりやすい識別子です。ApplicationID には、空白スペースや他の禁止されている文字が含まれていない任意のテキスト文字列を指定できます (有効な識別子を確実に作成するために、ApplicationID を指定するときには文字と数字だけを使用することをお勧めします)。Port パラメーターに割り当てる値も管理者が決定します。値として、使用可能な任意のネットワーク ポートを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4308e-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="4308e-137">信頼できるアプリケーションを作成した後、次のコマンドを実行して、Lync Server トポロジの変更を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="4308e-138">また、すべての SIP Uri ダイヤルプランに Exchange クライアントアクセスとメールボックスサーバーを追加する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4308e-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="4308e-139">これにより、サーバーが、Lync Server の ExUmRouting topology で信頼できる SIP ピアとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="4308e-140">**Outlook Web App でインスタント メッセージングを有効にする**</span><span class="sxs-lookup"><span data-stu-id="4308e-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="4308e-141">Lync サーバーが正しく構成されている場合は、Outlook Web App の構成を開始できます。</span><span class="sxs-lookup"><span data-stu-id="4308e-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="4308e-142">このプロセスの最初の手順は、フロントエンドサーバー上のすべての Outlook Web App 仮想ディレクトリでインスタントメッセージングを有効にすることです。</span><span class="sxs-lookup"><span data-stu-id="4308e-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="4308e-143">(バックエンドサーバーの仮想ディレクトリに対してインスタントメッセージングを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4308e-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="4308e-144">実際には、バックエンドサーバでインスタントメッセージを有効にしないことをお勧めします。)Exchange 管理シェル内から次のコマンドを実行して、クライアントアクセスサーバーでインスタントメッセージングを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4308e-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="4308e-p113">Outlook Web App をインストールすると、インスタント メッセージングは既定で有効になります。つまり、InstantMessagingEnabled プロパティは True に設定されます。ただし、上記のコマンドは、インスタント メッセージングの種類を OCS に設定する目的でも実行できます。既定では、InstantMessagingType は None に設定されています。</span><span class="sxs-lookup"><span data-stu-id="4308e-p113">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True. However, you must still run the preceding command in order to set the instant messaging type to OCS. By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="4308e-148">次に、次の2行を Outlook Web App web.config ファイルに追加する必要があります (このファイルは、通常\\、C\\:\\Program Files\\Microsoft\\Exchange Server\\V15 clientaccess Owa) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4308e-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="4308e-149">この2行は、web.config ファイルの\<AppSettings\>ノードの下に追加する必要があります。この手順は、Outlook Web App がインストールされているバックエンドサーバーでのみ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="4308e-150">上の例では、IMCertificateThumbprint の値はバックエンドサーバーにインストールされている Exchange 2013 証明書の拇印である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="4308e-151">この情報を取得するには、Exchange 管理シェルから次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4308e-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="4308e-152">また、IMServerName に割り当てられている値が、Outlook Web App の信頼されたアプリケーションプールを作成した Lync Server プールの完全修飾ドメイン名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4308e-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="4308e-153">Outlook Web App で使用する証明書は、Lync Server によって信頼されている証明書である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="4308e-154">証明書が Lync Server と Exchange の両方によって信頼されるようにする方法の1つは、内部の証明機関を使ってメールボックスサーバーで証明書を作成し、その FQDN がサブジェクト名に使用され、この FQDN が t に表示されるようにすることです。証明書の代替名フィールド。</span><span class="sxs-lookup"><span data-stu-id="4308e-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="4308e-155">作成された証明書はバックエンド サーバーにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="4308e-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="4308e-156">最終的には、同じ証明書が Exchange ユニファイドメッセージングと Lync Server 間の通信という2つの目的で使用されることになります。および 2) Outlook Web App と Lync Server の統合。</span><span class="sxs-lookup"><span data-stu-id="4308e-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="4308e-157">Web.config ファイルの更新後、Exchange バックエンドサーバーで次のコマンドを実行して、Outlook Web App pool をリサイクルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4308e-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="4308e-158">リサイクル操作が成功すると、Exchange 管理シェルに次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="4308e-159">**Outlook Web App メール ボックス ポリシーを構成する**</span><span class="sxs-lookup"><span data-stu-id="4308e-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="4308e-p117">この時点で、次のコマンドを使用して、適切な Outlook Web App メールボックス ポリシーでインスタント メッセージングを構成できます。たとえば、次のコマンドをメールボックス サーバーの 1 つで実行すると、既定のポリシーでインスタント メッセージングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="4308e-p117">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies). For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="4308e-162">また、次のコマンドを実行すると、すべての Outlook Web App メールボックス ポリシーでインスタント メッセージングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="4308e-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="4308e-163">メールボックスポリシーを有効にすると、そのポリシーによって管理されるすべてのユーザーは、次のような Lync Server と Outlook Web App の間で完全に統合されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="4308e-164">ユーザーが Exchange 2013 上にメールボックスを持っている。</span><span class="sxs-lookup"><span data-stu-id="4308e-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="4308e-165">ユーザーが Lync Server 2013 用に有効になっている。</span><span class="sxs-lookup"><span data-stu-id="4308e-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="4308e-166">ユーザーが有効な SIP プロキシ アドレスを使用している。</span><span class="sxs-lookup"><span data-stu-id="4308e-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="4308e-167">**Outlook Web App でインスタント メッセージングを無効にする**</span><span class="sxs-lookup"><span data-stu-id="4308e-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="4308e-168">既に説明したように、インスタント メッセージングは Outlook Web App で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4308e-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="4308e-169">つまり、Outlook Web App を Lync Server と統合していない場合は、ユーザーが Outlook Web App にログオンするたびに、空白のプレゼンスアイコンとエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="4308e-170">この問題を回避するには、次の Exchange 管理シェルコマンドを使用して、Outlook web App でインスタントメッセージングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4308e-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="4308e-171">**Outlook Web App との統合を確認する**</span><span class="sxs-lookup"><span data-stu-id="4308e-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="4308e-172">インスタント メッセージングとプレゼンスが Outlook Web App と統合されていることを確認するには、Outlook Web App 2013 にサインオンします。</span><span class="sxs-lookup"><span data-stu-id="4308e-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="4308e-173">画面の右上隅に、Exchange 表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4308e-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="4308e-174">名前の横にプレゼンスアイコンが表示されている場合 (たとえば、現在の状態が利用可能であることを示す緑色のアイコン)、Lync Server と Outlook Web App が正常に統合されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="4308e-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="4308e-175">Outlook Web App に最初にサインオンしたら、イベント ID 112 (およびソース MSExchange OWA) のイベントが、メールボックス サーバーのイベント ログに書き込まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4308e-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="4308e-176">このイベントは、インスタント メッセージング エンドポイント マネージャーが適切に初期化されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="4308e-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="4308e-177">インスタントメッセージングが機能していないように見える場合は、メールボックスサーバーで、\\フォルダー C: Program files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging のログファイルを探します。</span><span class="sxs-lookup"><span data-stu-id="4308e-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="4308e-178">Logging または InstantMessaging のどちらかのフォルダーが存在しない場合は、適切に統合されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="4308e-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="4308e-179">その場合は、Lync Server (すべてのレベルとすべてのフラグ) で SIPStack トレースを使用して、統合に失敗した理由を特定してください。</span><span class="sxs-lookup"><span data-stu-id="4308e-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

