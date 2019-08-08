---
title: 会議参加ページの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c01c2be988c94bd0bc90ed6b48702d426b42e505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="6e379-102">会議参加ページの構成</span><span class="sxs-lookup"><span data-stu-id="6e379-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e379-103">_**最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="6e379-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="6e379-104">ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかが検出されます。</span><span class="sxs-lookup"><span data-stu-id="6e379-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="6e379-105">クライアントが既にインストールされている場合は、そのクライアントが開き、会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="6e379-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="6e379-106">クライアントがインストールされていない場合、既定では、2013バージョンの Lync Web App が開きます。</span><span class="sxs-lookup"><span data-stu-id="6e379-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="6e379-107">ユーザーが Office Communicator 2007 R2 または Lync 2010 アテンダントを使って会議に参加できるようにする場合は、[会議参加] ページの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6e379-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="6e379-108">これらの構成オプションは、Lync Server 2013 コントロールパネルから削除されていますが、CsWebServiceConfiguration コマンドレットを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="6e379-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="6e379-109">会議の参加ページの CsWebServiceConfiguration パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e379-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e379-110">CsWebServiceConfiguration パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e379-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="6e379-111">説明</span><span class="sxs-lookup"><span data-stu-id="6e379-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e379-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="6e379-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="6e379-113">True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加するユーザーには、Office Communicator 2007 R2 を使用して会議に参加する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="6e379-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="6e379-114">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="6e379-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e379-115">Showalternatejoinoptionている</span><span class="sxs-lookup"><span data-stu-id="6e379-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="6e379-116">True に設定すると、オンライン会議に参加するための代替オプション (Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e379-116">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users.</span></span> <span data-ttu-id="6e379-117">False (既定値) に設定した場合、これらのオプションは使用できますが、ユーザーは自分のオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e379-117">When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="6e379-118">Lync Server 2013 管理シェルを使用して会議の参加ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="6e379-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="6e379-119">Lync Server 2013 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e379-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6e379-120">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e379-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="6e379-121">このコマンドレットは、web サービスの構成設定を返します。</span><span class="sxs-lookup"><span data-stu-id="6e379-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="6e379-122">次のコマンドを実行します。設定に応じてパラメーターが True または False に設定されています (このコマンドレットのパラメーターの詳細については、「Lync Server 2013 管理シェルドキュメント」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="6e379-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

