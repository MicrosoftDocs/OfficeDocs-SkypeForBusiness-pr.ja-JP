---
title: 'Lync Server 2013: グローバルホストボイスメールポリシーの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d0e29981df18ed883d6c33fb810d86da09d255
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="6a804-102">Lync Server 2013 でのグローバルホストボイスメールポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="6a804-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a804-103">_**トピックの最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="6a804-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="6a804-104">*グローバル*ホストボイスメールポリシーは、Lync Server 2013 と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6a804-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="6a804-105">グローバル ポリシーを必要に応じて変更することはできますが、名前変更や削除はできません。</span><span class="sxs-lookup"><span data-stu-id="6a804-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="6a804-106">グローバルポリシーを変更するには、Set-cshostedvoicemailpolicy コマンドレットを使用して、特定の展開についてパラメーターを適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="6a804-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="6a804-107">[Set-cshostedvoicemailpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)コマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a804-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="6a804-108">グローバルホストボイスメールポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="6a804-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="6a804-109">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a804-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6a804-110">Set-cshostedvoicemailpolicy コマンドレットを実行して、環境のグローバルポリシーパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="6a804-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="6a804-111">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a804-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="6a804-112">このコマンドではポリシーの Identity パラメーターが指定されていないため、Windows PowerShell コマンドラインインターフェイスでは、グローバルホストボイスメールポリシーに次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6a804-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="6a804-p103">**Destination** では、Hosted Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。このパラメーターは省略可能ですが、ユーザーに割り当てられているポリシーで送信先の値が設定されていないと、ユーザーのホスト ボイス メールを有効にしようとしても失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a804-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="6a804-115">**Organization** Lync Server ユーザーが所属する Exchange テナントのコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a804-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="6a804-116">各テナントは、Hosted Exchange UM サービス上のテナントの FQDN として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a804-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6a804-117">前の例のコマンドレットでは、値 "corp1.litwareinc.com" は、組織パラメーターに既に存在している可能性のある任意の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6a804-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="6a804-118">たとえば、ポリシーに組織のコンマ区切りの一覧が既に含まれている場合は、完全なリストが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6a804-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="6a804-119">リスト全体を置換するのではなく、リストに組織を追加する場合は、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6a804-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

