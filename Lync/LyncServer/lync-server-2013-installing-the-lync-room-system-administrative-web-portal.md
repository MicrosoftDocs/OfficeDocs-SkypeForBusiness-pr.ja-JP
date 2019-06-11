---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルをインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="1d8ee-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d8ee-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d8ee-103">_**最終更新日:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="1d8ee-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="1d8ee-104">Microsoft Lync Room System 管理 Web ポータルは、Microsoft ダウンロードセンターからダウンロードでき[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)ます。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="1d8ee-105">Lync Room System 管理 Web ポータルをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="1d8ee-106">Lync Server 管理シェルで次のコマンドレットを実行して、信頼されているアプリケーションポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="1d8ee-107">会議室ポータルをインストールするには、 **LyncRoomAdminPortal**をダウンロードしてから、管理者として実行します。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="1d8ee-108">Web.config ファイルを次の場所から開きます。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="1d8ee-109">% Program Files%\\Microsoft Lync Server 2013\\Web コンポーネント\\会議室ポータル\\の\\Int ハンドラー</span><span class="sxs-lookup"><span data-stu-id="1d8ee-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="1d8ee-110">Web.config ファイルで、「Lync Room System 管理ポータルの前提条件を設定する」のセクションの手順2で作成したユーザー名に PortalUserName を変更します (手順は LRSApp の推奨名)。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="1d8ee-111">LRS 管理ポータルは信頼できるアプリケーションであるため、ポータル構成でパスワードを入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="1d8ee-112">このユーザーがローカル レジストラーとは別のレジストラーを使用している場合、Web.Config ファイルで次の行を追加してレジストラを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="1d8ee-113">5061 以外のポートが使用されている場合は、Web.Config ファイルに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="1d8ee-114">Lync Room System 管理 Web ポータルのインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="1d8ee-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="1d8ee-115">Lync Room System 管理 Web ポータルのインストールを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="1d8ee-116">フロントエンド サーバーで、次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="1d8ee-117">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="1d8ee-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="1d8ee-118">下記の画像のように、エラーが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="1d8ee-119">![Lync Room System 管理ポータルのサインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System 管理ポータルのサインイン画面")</span><span class="sxs-lookup"><span data-stu-id="1d8ee-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="1d8ee-120">エラーが表示されない場合は、トポロジ内の他のいずれかのコンピューターから次の URL へのアクセスを試行します。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="1d8ee-121">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="1d8ee-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="1d8ee-122">このページにアクセスするには、「」の「自動クライアントサインイン用の DNS レコード」の説明に従って DNS レコードを[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d8ee-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

