---
title: 'Lync Server 2013: ブランチ サイト用の PSTN ゲートウェイの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4445647e6ffcbfc2cfc137bd120d0aced6a9908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="7e0de-102">Lync Server 2013 でのブランチ サイト用の PSTN ゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="7e0de-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e0de-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7e0de-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7e0de-104">この手順はセントラルサイトで実行します。これには、少なくとも1つのフロントエンドプールまたは Standard Edition サーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e0de-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e0de-105">この手順を実行する前に、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e0de-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="7e0de-106">Lync Server 2013&nbsp;通信ソフトウェアがセントラルサイトでセットアップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e0de-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="7e0de-107">仲介サーバーがセントラルサイトに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e0de-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="7e0de-108">PSTN ゲートウェイを定義するには</span><span class="sxs-lookup"><span data-stu-id="7e0de-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="7e0de-109">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server**]、[ **lync server Topology Builder**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e0de-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="7e0de-110">コンソールツリーで、[セントラルサイト]、[**ブランチオフィスサイト**] の順に展開し、公衆交換電話網 (PSTN) ゲートウェイを定義するブランチサイトの名前を展開して、[**共有コンポーネント**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="7e0de-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="7e0de-111">[ **PSTN ゲートウェイ**] を右クリックし、[**新しい IP/PSTN ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e0de-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="7e0de-112">[**新しい IP/PSTN ゲートウェイの定義**] ダイアログボックスで、[**ゲートウェイの FQDN または ip アドレス**] をクリックし、ブランチサイトで展開するゲートウェイの完全修飾ドメイン名 (FQDN) または ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7e0de-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="7e0de-113">[ **IP/PSTN ゲートウェイのリスニングポート**] をクリックし、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="7e0de-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="7e0de-114">[ **SIP トランスポートプロトコル**] ボックスの一覧で、ゲートウェイが使用するトランスポートプロトコルをクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e0de-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e0de-115">セキュリティ上の理由から、トランスポート層セキュリティ (TLS) をサポートする PSTN ゲートウェイを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e0de-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="7e0de-116"><STRONG>コマンドレットを使用</STRONG>して、PSTN ゲートウェイのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="7e0de-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="7e0de-117">詳しくは、「Lync Server 管理シェルのヘルプ」の「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7e0de-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="7e0de-118">ブランチサイトの回復の**次のステップ**: [Lync Server 2013 でブランチサイトの回復用ユーザーを構成する](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="7e0de-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7e0de-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e0de-119">See Also</span></span>


[<span data-ttu-id="7e0de-120">Lync Server 2013 の PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="7e0de-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

