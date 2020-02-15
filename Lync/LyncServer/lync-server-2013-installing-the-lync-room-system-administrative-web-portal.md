---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルのインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af0f52b940e9bcfb78048ef3a2c60f09d265073
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="a2116-102">Lync Server 2013 での Lync Room System 管理 Web ポータルのインストール</span><span class="sxs-lookup"><span data-stu-id="a2116-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2116-103">_**トピックの最終更新日:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="a2116-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="a2116-104">Microsoft Lync Room System 管理 Web ポータルは、Microsoft ダウンロードセンターからダウンロードでき[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)ます。</span><span class="sxs-lookup"><span data-stu-id="a2116-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="a2116-105">Lync Room System 管理 Web ポータルをインストールするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2116-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="a2116-106">Lync Server 管理シェルで次のコマンドレットを実行して、信頼されたアプリケーションポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="a2116-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="a2116-107">会議室ポータルをインストールするには、 **LyncRoomAdminPortal**をダウンロードして、管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="a2116-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="a2116-108">Web.config ファイルを次の場所から開きます。</span><span class="sxs-lookup"><span data-stu-id="a2116-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="a2116-109">% Program Files%\\Microsoft Lync Server 2013\\Web コンポーネント\\ミーティングルームポータル\\の\\Int ハンドラー</span><span class="sxs-lookup"><span data-stu-id="a2116-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="a2116-110">Web.config ファイルで、「Lync Room System 管理ポータルの前提条件の構成」のセクションの「手順2で作成したユーザー名に PortalUserName を変更します (この手順で推奨される名前は LRSApp です)。</span><span class="sxs-lookup"><span data-stu-id="a2116-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="a2116-111">LRS 管理ポータルは信頼されたアプリケーションであるため、ポータル構成でパスワードを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a2116-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="a2116-112">このユーザーがローカルレジストラーとは別のレジストラーを使用している場合は、Web.config ファイルに次の行を追加して、レジストラーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2116-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="a2116-113">使用しているポートが5061以外の場合は、web.config ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="a2116-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="a2116-114">Lync Room System 管理 Web ポータルのインストールの確認</span><span class="sxs-lookup"><span data-stu-id="a2116-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="a2116-115">Lync Room System 管理 Web ポータルのインストールを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a2116-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="a2116-116">フロントエンドサーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="a2116-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="a2116-117">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="a2116-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="a2116-118">次の図に示すように、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a2116-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="a2116-119">![Lync Room System 管理者ポータルのサインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System 管理者ポータルのサインイン画面")</span><span class="sxs-lookup"><span data-stu-id="a2116-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="a2116-120">エラーが表示されない場合は、トポロジ内の他のコンピュータから次の URL にアクセスしてみてください。</span><span class="sxs-lookup"><span data-stu-id="a2116-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="a2116-121">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="a2116-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="a2116-122">ページにアクセスするには、「」の「自動クライアントサインインに必要な DNS レコード」で説明されているように[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)、dns レコードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2116-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

