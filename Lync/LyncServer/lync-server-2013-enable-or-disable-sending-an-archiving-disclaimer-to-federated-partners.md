---
title: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
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
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="79065-102">Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化</span><span class="sxs-lookup"><span data-stu-id="79065-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79065-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="79065-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="79065-104">エッジサーバーを展開して組織のフェデレーションを有効にした時点で、アーカイブの免責事項をフェデレーションパートナーに自動的に送信するかどうかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79065-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="79065-105">外部通信をアーカイブする場合は、アーカイブの免責事項の送信を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79065-105">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="79065-106">この設定を変更するには、このトピックの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="79065-106">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="79065-107">次の手順では、組織のフェデレーションを既に有効にしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="79065-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="79065-108">フェデレーションを有効にする方法について詳しくは、展開ドキュメントまたは運用ドキュメントの「 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効</A>にする」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79065-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="79065-109">フェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="79065-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="79065-110">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="79065-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="79065-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="79065-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="79065-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79065-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="79065-113">左側のナビゲーションバーで、[**外部ユーザーアクセス**] をクリックし、[**アクセスエッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79065-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="79065-114">[**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79065-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="79065-115">[ **Access Edge 構成の編集**] の [**フェデレーションユーザーとの通信を有効**にする] で、[アーカイブの**免責事項をフェデレーションパートナーに送信**する] チェックボックスをオンまたはオフにして、アーカイブの免責事項の自動送信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="79065-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="79065-116">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79065-116">Click **Commit**.</span></span>

<span data-ttu-id="79065-117">フェデレーションされたユーザーが Lync Server 2013 の展開でユーザーと共同作業できるようにするには、フェデレーションされたユーザーアクセスをサポートするために、少なくとも1つの外部アクセスポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79065-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="79065-118">詳細については、展開ドキュメントまたは操作のドキュメントの「 [Lync Server 2013 で XMPP フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79065-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="79065-119">特定のフェデレーションドメインのアクセス制御の詳細については、「展開ドキュメントまたは操作のドキュメントの「 [Lync Server 2013 で許可されている外部ドメインのサポートを構成する](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79065-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="79065-120">Windows PowerShell コマンドレットを使用してアーカイブ免責事項を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="79065-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="79065-121">アーカイブ免責事項の使用は、Windows PowerShell と CsAccessEdgeConfiguration コマンドレットを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="79065-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="79065-122">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="79065-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="79065-123">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="79065-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="79065-124">アーカイブの免責事項を有効にするには</span><span class="sxs-lookup"><span data-stu-id="79065-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="79065-125">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="79065-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="79065-126">アーカイブの免責事項を無効にするには</span><span class="sxs-lookup"><span data-stu-id="79065-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="79065-127">アーカイブについての免責事項を無効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="79065-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

