---
title: Kerberos 認証アカウントのパスワードを IIS に同期させる
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 255c1035809b69d5de1bb5e08fc770dc9a6b1c4d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a><span data-ttu-id="e527a-102">Lync Server 2013 で Kerberos 認証アカウントのパスワードを IIS に同期させる</span><span class="sxs-lookup"><span data-stu-id="e527a-102">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e527a-103">_**トピックの最終更新日:** 2010-11-08_</span><span class="sxs-lookup"><span data-stu-id="e527a-103">_**Topic Last Modified:** 2010-11-08_</span></span>

<span data-ttu-id="e527a-104">この手順を正常に完了させるには、RTCUniversalServerAdmins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e527a-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="e527a-105">サイトでは、フロントエンドサーバー、Standard Edition サーバー、およびディレクターは、Web サービスへの要求を認証する目的で、Kerberos 認証アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e527a-105">In a site, Front End Servers, Standard Edition servers, and Directors can use a Kerberos authentication account for purposes of authenticating requests to the Web Services service.</span></span> <span data-ttu-id="e527a-106">この手順では、Kerberos アカウントが割り当てられているサイトで Web サービスを実行している各サーバーを検索し、Kerberos アカウントを使用するようにインターネットインフォメーションサービス (IIS) の構成設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="e527a-106">This procedure locates each server running Web Services in a site that has been assigned a Kerberos account and updates the Internet Information Services (IIS) configuration settings to use the Kerberos account.</span></span> <span data-ttu-id="e527a-107">詳細については、「 [Lync server 2013 のサーバーでの Kerberos 認証アカウントパスワードの設定](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e527a-107">For details, see [Set a Kerberos authentication account password on a server in Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).</span></span>

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a><span data-ttu-id="e527a-108">Kerberos 認証アカウントのパスワードを設定および構成するには</span><span class="sxs-lookup"><span data-stu-id="e527a-108">To set and configure a Kerberos authentication account password</span></span>

1.  <span data-ttu-id="e527a-109">ソース コンピューター (fe01.contoso.com など) に RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="e527a-109">Log on to a source computer (such as fe01.contoso.com) as a member of RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e527a-110">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e527a-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e527a-111">Lync Server 管理シェルコマンドラインから、次の2つのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e527a-111">From the Lync Server Management Shell command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    <span data-ttu-id="e527a-112">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="e527a-112">For example:</span></span>
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e527a-p102">ソース コンピューターと宛先のコンピューターの名前は、サーバーの完全修飾ドメイン名 (FQDN) である必要があります。 プール名がソース コンピューターまたは宛先のコンピューターとして使用しているコンピューターの名前と同じでない限り、プール FQDN を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e527a-p102">The name of the source computer and destination computer must be a fully qualified domain (FQDN) name of the server. You cannot use the pool FQDN unless the pool name is the same as the name of the computer that you are using as a source computer or destination computer.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e527a-115">アカウントの追加、アカウントの削除など、Kerberos 認証に変更を加えた後、Lync Server 管理シェルコマンドプロンプトから<STRONG>Enable-CsTopology</STRONG>設定を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e527a-115">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

