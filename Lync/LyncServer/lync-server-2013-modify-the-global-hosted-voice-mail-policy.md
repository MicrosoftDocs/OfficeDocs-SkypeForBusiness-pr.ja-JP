---
title: 'Lync Server 2013: グローバルでホストされるボイスメールのポリシーを変更する'
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
ms.openlocfilehash: e930e0b1f9a6e2d246a8011c59e2c92c75ba138d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="7ae05-102">Lync Server 2013 でグローバルにホストされるボイスメールのポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="7ae05-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ae05-103">_**最終更新日:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="7ae05-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="7ae05-104">*グローバル*にホストされるボイスメールポリシーは、Lync Server 2013 と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7ae05-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="7ae05-105">必要に応じて変更できますが、名前の変更や削除はできません。</span><span class="sxs-lookup"><span data-stu-id="7ae05-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="7ae05-106">グローバルポリシーを変更するには、CsHostedVoicemailPolicy コマンドレットを使用して、特定の展開用にパラメーターを適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="7ae05-107">[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)コマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ae05-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="7ae05-108">グローバルでホストされるボイスメールのポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="7ae05-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="7ae05-109">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ae05-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7ae05-110">環境のグローバルポリシーパラメーターを設定するには、CsHostedVoicemailPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="7ae05-111">たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="7ae05-112">このコマンドによってポリシーの Id パラメーターが指定されないため、Windows PowerShell のコマンドラインインターフェイスでは、グローバルにホストされるボイスメールポリシーで次の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="7ae05-113">[ **Destination** ] は、ホストされた Exchange UM サービスの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-113">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="7ae05-114">このパラメーターは省略可能ですが、ホストされたボイスメールに対してユーザーを有効にしようとしても、ユーザーに割り当てられているポリシーに送信先の値がない場合、有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7ae05-114">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="7ae05-115">[**組織**] は、Lync Server ユーザーがホームである Exchange テナントのコンマ区切りリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="7ae05-116">各テナントは、ホストされた Exchange UM サービスでそのテナントの FQDN として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ae05-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ae05-117">前の例のコマンドレットでは、"corp1.litwareinc.com" という値が組織のパラメーターに存在する可能性がある値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="7ae05-117">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter.</span></span> <span data-ttu-id="7ae05-118">たとえば、ポリシーに既に組織のコンマ区切りのリストが含まれている場合は、完全な一覧が置換されます。</span><span class="sxs-lookup"><span data-stu-id="7ae05-118">For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced.</span></span> <span data-ttu-id="7ae05-119">リスト全体を置換するのではなく、リストに組織を追加する場合は、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7ae05-119">If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
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

