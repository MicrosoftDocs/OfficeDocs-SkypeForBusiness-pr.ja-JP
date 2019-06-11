---
title: Kerberos 認証アカウント パスワードと IIS との同期
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="0976e-102">Lync Server 2013 での Kerberos 認証アカウント パスワードと IIS との同期</span><span class="sxs-lookup"><span data-stu-id="0976e-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0976e-103">_**最終更新日:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="0976e-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="0976e-104">この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0976e-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="0976e-105">サイトでは、フロントエンドサーバー、標準エディションサーバー、およびディレクターは、Web サービスサービスへの要求を認証するために、Kerberos 認証アカウントを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="0976e-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="0976e-106">この手順では、Kerberos アカウントが割り当てられているサイトで Web サービスを実行している各サーバーを特定し、その Kerberos アカウントを使用するようにインターネットインフォメーションサービス (IIS) 構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="0976e-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="0976e-107">詳細については、「 [Lync server 2013 でサーバー上の Kerberos 認証アカウントパスワードを設定する](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0976e-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="0976e-108">Kerberos 認証アカウントのパスワードを設定および構成するには</span><span class="sxs-lookup"><span data-stu-id="0976e-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="0976e-109">ソースコンピューター (fe01.contoso.com など) に RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="0976e-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0976e-110">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0976e-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0976e-111">Lync Server 管理シェルコマンドラインから次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0976e-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="0976e-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0976e-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0976e-113">ソースコンピューターとターゲットコンピューターの名前は、サーバーの完全修飾ドメイン (FQDN) 名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0976e-113">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server.</span></span> <span data-ttu-id="0976e-114">プール名は、ソースコンピューターまたは移行先コンピューターとして使用しているコンピューターの名前と同じである場合を除き、プールの FQDN は使用できません。</span><span class="sxs-lookup"><span data-stu-id="0976e-114">You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0976e-115">アカウントの追加やアカウントの削除など、Kerberos 認証を変更した後は、Lync Server 管理シェルのコマンドプロンプトから、 <STRONG>Enable-CsTopology</STRONG>方法を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0976e-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

