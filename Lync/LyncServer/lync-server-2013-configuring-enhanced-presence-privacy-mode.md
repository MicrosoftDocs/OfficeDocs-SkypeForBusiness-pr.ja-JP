---
title: 'Lync Server 2013: 拡張プレゼンスプライバシーモードの構成'
description: 'Lync Server 2013: 拡張プレゼンスプライバシーモードの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8eab347d233c23a9a4becf119dee673d3021dfa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548453"
---
# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="673d7-103">Lync Server 2013 での拡張プレゼンスプライバシーモードの構成</span><span class="sxs-lookup"><span data-stu-id="673d7-103">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="673d7-104">_**トピックの最終更新日:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="673d7-104">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="673d7-105">拡張プレゼンスプライバシーモードを使用すると、ユーザーは自分のプレゼンス情報を制限して、Lync 2013 の連絡先リストに記載されている連絡先のみが表示されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="673d7-105">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="673d7-106">**Get-csprivacyconfiguration 戻し**   および**get-csprivacyconfiguration 戻し**コマンドレットでは、このオプションを制御する enableprivacymode パラメーターが設定されています。</span><span class="sxs-lookup"><span data-stu-id="673d7-106">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="673d7-107">EnablePrivacyMode が True に設定されている場合は、連絡先にプレゼンス情報を制限するオプションが Lync 2013 ステータスオプションで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="673d7-107">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="673d7-108">EnablePrivacyMode が False に設定されている場合は、ユーザーがすべてのユーザーに対して自身のプレゼンス情報を常に表示できるようにするか、あるいは管理者がプライバシー モードに加える今後の変更に従うかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="673d7-108">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="673d7-109">Lync 2013 および Lync 2010 のプライバシー設定は、以前のバージョンでは受け入れられません (Microsoft Office Communicator 2007 R2 または Microsoft Office Communicator 2007)。</span><span class="sxs-lookup"><span data-stu-id="673d7-109">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="673d7-110">以前のバージョンの Office Communicator でサインインが許可されている場合は、表示が許可されていないユーザーが Lync 2013 ユーザーの状態、連絡先情報、または画像を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="673d7-110">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="673d7-111">また、Lync 2013 ユーザーのプライバシー設定は、後で以前のバージョンの Communicator を使用してサインインした場合にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="673d7-111">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="673d7-112">これらの理由から、移行シナリオでは、拡張プレゼンス プライバシー モードを有効にする前に、以下のことを実行してください。</span><span class="sxs-lookup"><span data-stu-id="673d7-112">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="673d7-113">すべてのユーザーに Lync 2013 がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="673d7-113">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="673d7-114">Communicator の以前のバージョンによるサインインを回避する、クライアント バージョンのポリシー ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="673d7-114">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="673d7-115">拡張プレゼンス プライバシー モードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="673d7-115">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="673d7-116">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="673d7-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="673d7-117">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="673d7-117">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="673d7-118">このコマンドによって、組織で現在使用されているすべてのプライバシー構成設定のプライバシー モードが有効になります。</span><span class="sxs-lookup"><span data-stu-id="673d7-118">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="673d7-119">Lync Server 拡張プレゼンスプライバシーモードのポリシー構成が Lync 2013 クライアントの連絡先プレゼンスを管理する方法の詳細については、Microsoft サポート技術情報の記事「 [Lync server enhanced プレゼンスプライバシーモードを有効にする」を参照してください。一部の lync 連絡先のプレゼンス状態が "利用不可" に更新](https://support.microsoft.com/kb/3020057)されます。</span><span class="sxs-lookup"><span data-stu-id="673d7-119">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](https://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="673d7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="673d7-120">See Also</span></span>


[<span data-ttu-id="673d7-121">Get-csprivacyconfiguration 戻し</span><span class="sxs-lookup"><span data-stu-id="673d7-121">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="673d7-122">Get-csprivacyconfiguration 戻し</span><span class="sxs-lookup"><span data-stu-id="673d7-122">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="673d7-123">Get-csprivacyconfiguration 戻し</span><span class="sxs-lookup"><span data-stu-id="673d7-123">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

