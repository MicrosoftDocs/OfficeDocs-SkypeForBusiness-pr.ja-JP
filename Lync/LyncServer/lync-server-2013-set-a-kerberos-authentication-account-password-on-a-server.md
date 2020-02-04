---
title: 'Lync Server 2013: サーバーへの Kerberos 認証アカウント パスワードの設定'
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
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="d2c55-102">Lync Server 2013 でのサーバーへの Kerberos 認証アカウント パスワードの設定</span><span class="sxs-lookup"><span data-stu-id="d2c55-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c55-103">_**最終更新日:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="d2c55-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="d2c55-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c55-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="d2c55-105">フロントエンドサーバー、標準エディションサーバー、およびディレクターがある各サイトの Kerberos アカウントでパスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c55-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="d2c55-106">パスワードを設定するには、サイト内の1つのサーバー (たとえば、1つのフロントエンドサーバー) に対して、 **set-cskerberosaccountpassword** Windows PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="d2c55-107">各サイトについて、 **Set-csker"@ accountpassword** " コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c55-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="d2c55-108">Web サービス用のインターネットインフォメーションサービス (IIS) を構成し、Active Directory ドメインサービスのコンピューターアカウントにパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="d2c55-109">コマンドレットで使用されるパラメーターに基づいた代替メソッドは、Kerberos アカウントのパスワードのソースとして構成されている別のサーバーを使用しているときに、あるサーバーで IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="d2c55-110">**Set-Cskerの**コマンドレットを使用してパスワードを設定すると、Kerberos はパスワードをランダムに生成された文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="d2c55-111">このコマンドレットは、このアカウントが割り当てられているすべての Lync Server 2013 セントラルサイト内のすべての IIS インスタンスに接続します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="d2c55-112">Kerberos 認証アカウントのパスワードを設定するには</span><span class="sxs-lookup"><span data-stu-id="d2c55-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="d2c55-113">RTCUniversalServerAdmins グループのメンバーとしてインストールされている Lync Server 管理シェルがインストールされている任意のドメインコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d2c55-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d2c55-114">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d2c55-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d2c55-115">コマンドラインで、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="d2c55-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d2c55-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d2c55-117">UserAccount パラメーターを指定するには、Domain\User 形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c55-117">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="d2c55-118">Kerberos 認証のために作成されたコンピューターオブジェクトを参照する場合、User@Domain 拡張子形式はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d2c55-118">The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d2c55-119">アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2c55-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

