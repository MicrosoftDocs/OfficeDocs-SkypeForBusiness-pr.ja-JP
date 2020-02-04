---
title: 'Lync Server 2013: 新しい信頼できるアプリケーションサーバーを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="39b7c-102">Lync Server 2013 で新しい信頼できるアプリケーションサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="39b7c-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b7c-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="39b7c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="39b7c-104">信頼されたアプリケーションは、microsoft Lync Server 2013 によって信頼されている Microsoft ユニファイドコミュニケーションマネージ API (UCMA) 3.0 コア SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="39b7c-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="39b7c-105">UCMA アプリケーションの詳細については、の「ユニファイドコミュニケーションマネージ API 3.0 Core [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)SDK ドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b7c-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="39b7c-106">Microsoft Outlook Web Access (OWA) および Lync Server 2013 の構成の詳細については、Microsoft Exchange Server 2013 ドキュメントの「Outlook Web App および Lync Server 2010 の統合を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b7c-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="39b7c-107">トポロジの公開、有効化、または無効化を成功させるには、サーバーの役割を追加または削除するときに、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39b7c-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="39b7c-108">また、サーバーの役割を追加するための適切な管理者権限と権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="39b7c-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="39b7c-109">詳細については、展開ドキュメントの「 [Lync Server 2013 でのセットアップ権限の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39b7c-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="39b7c-110">その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="39b7c-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="39b7c-111">信頼できるアプリケーションサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="39b7c-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="39b7c-112">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="39b7c-113">トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="39b7c-114">[**既存の展開からトポロジをダウンロード**] を選び、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="39b7c-115">[名前を付け**てトポロジを保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="39b7c-116">左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼できるアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="39b7c-117">信頼されているアプリケーションプールの**プール FQDN**を入力し、それが単一サーバーか複数サーバーかを選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="39b7c-118">**[次ホップの選択**] ページで、一覧から Lync Server 2013 フロントエンドプールを選びます。</span><span class="sxs-lookup"><span data-stu-id="39b7c-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="39b7c-119">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="39b7c-120">トップノードの**Lync Server 2013**を選択し、[**操作**] メニューの [**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39b7c-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="39b7c-121">**信頼できるアプリケーションプール**が正常に作成され、正しいフロントエンドプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39b7c-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

