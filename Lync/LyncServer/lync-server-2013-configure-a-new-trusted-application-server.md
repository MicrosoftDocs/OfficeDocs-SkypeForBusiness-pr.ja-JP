---
title: 'Lync Server 2013: 新しい信頼されたアプリケーションサーバーの構成'
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
ms.openlocfilehash: 9f4d01e817e1a874af8c6beccdee332f85cc79ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="6b4ba-102">Lync Server 2013 で新しい信頼されたアプリケーションサーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="6b4ba-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b4ba-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6b4ba-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6b4ba-104">信頼されたアプリケーションは、microsoft Lync Server 2013 によって信頼されている Microsoft 統合コミュニケーション Managed API (UCMA) 3.0 コア SDK に基づくアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6b4ba-105">UCMA アプリケーションの詳細については、「ユニファイドコミュニケーション Managed API 3.0 Core SDK [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320)Documentation」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [https://go.microsoft.com/fwlink/p/?linkId=210320](https://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="6b4ba-106">Microsoft Outlook Web Access (OWA) および Lync Server 2013 の構成の詳細については、Microsoft Exchange Server 2013 のドキュメントの「Outlook Web App および Lync Server 2010 の統合を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="6b4ba-107">サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="6b4ba-108">サーバーの役割を追加するための、適切な管理者アクセス許可および権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="6b4ba-109">詳細については、「展開」のドキュメントの「 [Delegate setup permissions In Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="6b4ba-110">他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="6b4ba-111">信頼されたアプリケーションサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="6b4ba-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="6b4ba-112">トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="6b4ba-113">トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="6b4ba-114">[**既存の展開からトポロジをダウンロードする**] を選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="6b4ba-115">[**トポロジを名前を付けて保存**] ダイアログボックスで、使用するトポロジビルダーファイルをクリックし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="6b4ba-116">左側のウィンドウで、[**信頼されたアプリケーションサーバー**] を右クリックし、[**新しい信頼済みアプリケーションプール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="6b4ba-117">信頼済みアプリケーション プールの [**プールの FQDN**] を入力してから、単一サーバーにするか複数サーバーにするかを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="6b4ba-118">[**次ホップの選択**] ページで、リストから Lync Server 2013 フロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="6b4ba-119">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="6b4ba-120">トップノードの [ **Lync Server 2013**] を選択し、[**操作**] メニューの [**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="6b4ba-121">信頼された**アプリケーションプール**が正常に作成され、適切なフロントエンドプールに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4ba-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

