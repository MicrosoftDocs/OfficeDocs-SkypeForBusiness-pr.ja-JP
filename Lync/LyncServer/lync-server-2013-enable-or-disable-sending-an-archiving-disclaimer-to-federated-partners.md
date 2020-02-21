---
title: フェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0715a7fc0dd9ab81d84fd996d5b87682af3f69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="da144-102">Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="da144-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da144-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="da144-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="da144-p101">エッジ サーバーを展開し、組織に対してフェデレーションを有効にした時点で、フェデレーション パートナーにアーカイブについての免責事項を自動で送信するかどうかを指定する必要があります。 外部通信をアーカイブする場合は、アーカイブについての免責事項の送信を有効にする必要があります。 このトピックの手順を使用して、この構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="da144-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="da144-107">次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="da144-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="da144-108">フェデレーションを有効にする方法の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でリモートユーザーアクセスを有効または無効</A>にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da144-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="da144-109">フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="da144-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="da144-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="da144-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="da144-111">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="da144-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="da144-112">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da144-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="da144-113">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da144-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="da144-114">[**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da144-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="da144-115">[**アクセス エッジ構成の編集**] の [**フェデレーション ユーザーとの通信を有効にする**] で、[**フェデレーション パートナーにアーカイブについての免責事項を送信する**] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="da144-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="da144-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da144-116">Click **Commit**.</span></span>

<span data-ttu-id="da144-117">フェデレーションユーザーが Lync Server 2013 展開内のユーザーと共同作業できるようにするには、フェデレーションユーザーアクセスをサポートするために少なくとも1つの外部アクセスポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da144-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="da144-118">詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da144-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="da144-119">特定のフェデレーションドメインのアクセス制御の詳細については、「展開」のドキュメントまたは「操作」のドキュメントの「 [Configure support for allowed external domains In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da144-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da144-120">Windows PowerShell コマンドレットを使用してアーカイブの免責事項を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="da144-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="da144-121">アーカイブ免責事項の使用は、Windows PowerShell と Set-csaccessedgeconfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="da144-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="da144-122">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="da144-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="da144-123">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="da144-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="da144-124">アーカイブについての免責事項を有効にするには</span><span class="sxs-lookup"><span data-stu-id="da144-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="da144-125">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="da144-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="da144-126">アーカイブについての免責事項を無効にするには</span><span class="sxs-lookup"><span data-stu-id="da144-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="da144-127">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="da144-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

