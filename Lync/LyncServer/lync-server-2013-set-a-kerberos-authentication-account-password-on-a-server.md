---
title: 'Lync Server 2013: サーバーで Kerberos 認証アカウントのパスワードを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeef318392540aaa0600a4b61f20a296df25ca5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="02b68-102">Lync Server 2013 のサーバーで Kerberos 認証アカウントのパスワードを設定する</span><span class="sxs-lookup"><span data-stu-id="02b68-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02b68-103">_**トピックの最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="02b68-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="02b68-104">この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b68-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="02b68-105">フロントエンド サーバー、Standard Edition サーバー、およびディレクターが存在する各サイトの Kerberos アカウントにパスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b68-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="02b68-106">パスワードを設定するには、サイト内の1つのサーバー (たとえば、1つのフロントエンドサーバー) で、 **set-csker' osaccountpassword** Windows PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="02b68-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="02b68-107">サイトごとに、 **Set-cskerの osaccountpassword** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b68-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="02b68-108">このコマンドレットにより、Web サービスサービスのインターネットインフォメーションサービス (IIS) が構成され、Active Directory ドメインサービスのコンピューターアカウントのパスワードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="02b68-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="02b68-109">Kerberos アカウント パスワードのソースとして構成された別のサーバーを使用しながら、コマンドレットと使用されるパラメーターに基づいて、別のメソッドが 1 台のサーバーで IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="02b68-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="02b68-110">**Set-CsKerberosAccountPassword** コマンドレットを使用してパスワードを設定する場合、Kerberos はランダムに生成されたストリングをパスワードに設定します。</span><span class="sxs-lookup"><span data-stu-id="02b68-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="02b68-111">このコマンドレットは、このアカウントが割り当てられているすべての Lync Server 2013 中央サイト内のすべての IIS インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="02b68-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="02b68-112">Kerberos 認証アカウントのパスワードを設定するには</span><span class="sxs-lookup"><span data-stu-id="02b68-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="02b68-113">Lync Server 管理シェルがインストールされている任意のドメインコンピュータに、RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="02b68-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="02b68-114">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="02b68-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="02b68-115">コマンド ラインで次の 2 つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="02b68-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="02b68-116">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="02b68-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02b68-p103">UserAccount パラメーターは、ドメイン\ユーザーの形式で指定する必要があります。 Kerberos 認証目的で作成されたコンピューター オブジェクトの参照には、「ユーザー@ドメイン.拡張子」形式はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02b68-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="02b68-119">アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから<STRONG>Enable-CsTopology</STRONG>設定を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02b68-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

