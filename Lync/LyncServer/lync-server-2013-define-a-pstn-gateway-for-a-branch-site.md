---
title: 'Lync Server 2013: ブランチサイト用の PSTN ゲートウェイの定義'
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
ms.openlocfilehash: 435af3ab537097592325438707b89ce901da9bcd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516394"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="98c9a-102">Lync Server 2013 でのブランチサイト用の PSTN ゲートウェイの定義</span><span class="sxs-lookup"><span data-stu-id="98c9a-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c9a-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="98c9a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="98c9a-104">この手順は、少なくとも1つのフロントエンドプールまたは Standard Edition サーバーが含まれるセントラルサイトで実行してください。</span><span class="sxs-lookup"><span data-stu-id="98c9a-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98c9a-105">手順を実行する前に、以下の条件が整っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c9a-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="98c9a-106">Lync Server 2013 &nbsp; 通信ソフトウェアは、セントラルサイトで設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c9a-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="98c9a-107">中央サイトに仲介サーバーを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98c9a-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="98c9a-108">PSTN ゲートウェイを定義するには</span><span class="sxs-lookup"><span data-stu-id="98c9a-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="98c9a-109">[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c9a-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="98c9a-110">コンソール ツリーで中央サイトを展開して、[**ブランチ オフィス サイト**] を展開し、公衆交換電話網 (PSTN) ゲートウェイを定義するブランチ サイトの名前を展開し、次に [**共有コンポーネント**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="98c9a-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="98c9a-111">[**PSTN ゲートウェイ**] を右クリックして、[**新しい IP/PSTN ゲートウェイ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c9a-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="98c9a-112">[**新しい IP/PSTN ゲートウェイの定義**] ダイアログ ボックスで、[**ゲートウェイ FQDN または IP アドレス**] をクリックして、ブランチ サイトに展開するゲートウェイの完全修飾ドメイン名 (FQDN) または IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="98c9a-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="98c9a-113">[**IP/PSTN ゲートウェイのリッスン ポート**] をクリックして、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="98c9a-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="98c9a-114">[**SIP トランスポート プロトコル**] リストで、ゲートウェイで使用するトランスポート プロトコルをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98c9a-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c9a-115">セキュリティ上の理由のため、トランスポート層セキュリティ (TLS) をサポートする PSTN ゲートウェイの使用を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98c9a-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="98c9a-116">コマンドレット <STRONG>Set-CsPstnGateway</STRONG> を使用して、PSTN ゲートウェイのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="98c9a-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="98c9a-117">詳細については、「Lync Server 管理シェルのヘルプ」の「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98c9a-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="98c9a-118">ブランチサイトの復元の**次のステップ**: [Lync Server 2013 でのブランチサイトの復元のユーザーの構成](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="98c9a-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98c9a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="98c9a-119">See Also</span></span>


[<span data-ttu-id="98c9a-120">Lync Server 2013 の PSTN ゲートウェイの展開オプション</span><span class="sxs-lookup"><span data-stu-id="98c9a-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

