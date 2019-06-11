---
title: 'Lync Server 2013: 既存のレジストラー構成設定を削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9fe0ee46ff823a5184ee79f3b06bb02bb68115d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fe1b1-102">Lync Server 2013 で既存のレジストラー構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="fe1b1-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe1b1-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fe1b1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fe1b1-104">レジストラーを削除するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="fe1b1-105">レジストラー構成設定を削除するには</span><span class="sxs-lookup"><span data-stu-id="fe1b1-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="fe1b1-106">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fe1b1-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe1b1-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe1b1-109">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**レジストラー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="fe1b1-110">[**レジストラー**] ページの検索フィールドに、削除するレジストラーの名前の全体または一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="fe1b1-111">一覧で、対象のレジストラーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="fe1b1-112">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fe1b1-113">Windows PowerShell コマンドレットを使用してレジストラー構成設定を削除する</span><span class="sxs-lookup"><span data-stu-id="fe1b1-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fe1b1-114">レジストラーの構成設定は、Windows PowerShell と**CsProxyConfiguration**コマンドレットを使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="fe1b1-115">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fe1b1-116">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="fe1b1-117">レジストラーのセキュリティ設定の特定のセットを削除するには</span><span class="sxs-lookup"><span data-stu-id="fe1b1-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="fe1b1-118">次のコマンドは、エッジ サーバー atl-edge-011.litwareinc.com に適用されるレジストラーのセキュリティ設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="fe1b1-119">サイト スコープに適用されるレジストラーのセキュリティ設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="fe1b1-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="fe1b1-120">次のコマンドは、レジストラー サービスに適用されるすべてのレジストラーのセキュリティ設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="fe1b1-121">NTLM 認証を許可するレジストラーのセキュリティ設定をすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="fe1b1-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="fe1b1-122">次のコマンドは、クライアント認証に NTLM の使用を許可するレジストラーのセキュリティ設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="fe1b1-123">詳しくは、「 [CsProxyConfiguration の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fe1b1-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

