---
title: 'Lync Server 2013: 会議参加ページの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting join page
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48184037
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 872e95c1d5254830a80b8a0d0dd84b233f2d1813
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-join-page-in-lync-server-2013"></a><span data-ttu-id="6bec8-102">Lync Server 2013 での会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="6bec8-102">Configuring the meeting join page in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bec8-103">_**トピックの最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="6bec8-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="6bec8-104">ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページによって、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかが検出されます。</span><span class="sxs-lookup"><span data-stu-id="6bec8-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="6bec8-105">クライアントがすでにインストールされている場合、クライアントがミーティングを開き、参加します。</span><span class="sxs-lookup"><span data-stu-id="6bec8-105">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="6bec8-106">クライアントがインストールされていない場合、既定では、2013バージョンの Lync Web App が開きます。</span><span class="sxs-lookup"><span data-stu-id="6bec8-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="6bec8-107">ユーザーが Office Communicator 2007 R2 または Lync 2010 アテンダントを使用して会議に参加できるようにする場合は、会議参加ページの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6bec8-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="6bec8-108">これらの構成オプションは Lync Server 2013 コントロールパネルから削除されましたが、Set-cswebserviceconfiguration コマンドレットを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="6bec8-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-set-cswebserviceconfiguration-parameters"></a><span data-ttu-id="6bec8-109">ミーティング参加ページの Set-CsWebServiceConfiguration パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bec8-109">Meeting Join Page Set-CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bec8-110">Set-CsWebServiceConfiguration パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bec8-110">Set-CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="6bec8-111">説明</span><span class="sxs-lookup"><span data-stu-id="6bec8-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bec8-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="6bec8-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="6bec8-113">True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加しているユーザーには、Office Communicator 2007 R2 を使用して会議に参加する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="6bec8-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="6bec8-114">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="6bec8-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bec8-115">Showalternatejoinoptionsexpan</span><span class="sxs-lookup"><span data-stu-id="6bec8-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="6bec8-p104">True に設定した場合、オンライン会議に参加するための別のオプション (Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。False (既定値) に設定されている場合、これらのオプションは使用可能ですが、ユーザーが自分でオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6bec8-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="6bec8-118">Lync Server 2013 管理シェルを使用して会議参加ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="6bec8-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="6bec8-119">Lync Server 2013 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6bec8-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6bec8-120">Web サービス構成設定を表示するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6bec8-120">To view the web service configuration settings, run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration

3.  <span data-ttu-id="6bec8-121">ユーザーの設定に応じて、パラメーターを True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、「 [set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) In Lync Server 2013 Management Shell documentation」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="6bec8-121">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration) in the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6bec8-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bec8-122">See Also</span></span>


[<span data-ttu-id="6bec8-123">Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="6bec8-123">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

