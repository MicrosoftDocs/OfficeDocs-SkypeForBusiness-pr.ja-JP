---
title: 'Lync Server 2013: コマンドレットの使用によるドメインの準備の無効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="6cccc-102">Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化</span><span class="sxs-lookup"><span data-stu-id="6cccc-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cccc-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6cccc-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6cccc-104">[無効にする] **-CsAdDomain**コマンドレットを使用して、ドメインの準備手順を逆にします。</span><span class="sxs-lookup"><span data-stu-id="6cccc-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="6cccc-105">コマンドレットを使用してドメインの準備を逆にするには</span><span class="sxs-lookup"><span data-stu-id="6cccc-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="6cccc-106">Domain Admins グループのメンバーとして、ドメイン内の任意のサーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6cccc-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6cccc-107">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cccc-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6cccc-108">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6cccc-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="6cccc-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6cccc-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="6cccc-110">Force パラメーターが存在する場合、ドメイン内の1つ以上のフロントエンドサーバーまたは A/V 会議サーバーがアクティブ化されている場合でも、ドメインの準備はロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="6cccc-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="6cccc-111">Force パラメーターが存在しない場合、ドメイン内のフロントエンドサーバーまたは A/V 会議サーバーがアクティブ化されていると、ドメインの準備のロールバックが終了します。</span><span class="sxs-lookup"><span data-stu-id="6cccc-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6cccc-112">Parameter GlobalSettingsDomainController を使うと、グローバル設定が保存されている場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6cccc-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="6cccc-113">設定がシステムコンテナーに保存されている場合 (つまり、グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、Active Directory フォレストのルートでドメインコントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6cccc-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="6cccc-114">グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6cccc-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6cccc-115">このパラメーターを指定しない場合、設定は構成コンテナーに保存され、AD&nbsp;DS の任意のドメインコントローラーを参照することがコマンドレットによって想定されます。</span><span class="sxs-lookup"><span data-stu-id="6cccc-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6cccc-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cccc-116">See Also</span></span>


[<span data-ttu-id="6cccc-117">Lync Server 2013 のドメイン準備手続き</span><span class="sxs-lookup"><span data-stu-id="6cccc-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="6cccc-118">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="6cccc-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

