---
title: ミーティング参加ページを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the meeting join page
ms:assetid: 036c9d03-ad95-4d63-a3d8-6cae1a8ad530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204635(v=OCS.15)
ms:contentKeyID: 48183260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03ec9602912d8969c57d86aa862c7bd833585d21
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="f020a-102">ミーティング参加ページを構成する</span><span class="sxs-lookup"><span data-stu-id="f020a-102">Configure the meeting join page</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f020a-103">_**トピックの最終更新日:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="f020a-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="f020a-104">ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページによって、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかが検出されます。</span><span class="sxs-lookup"><span data-stu-id="f020a-104">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Lync 2013 client is already installed on the user’s computer.</span></span> <span data-ttu-id="f020a-105">クライアントがすでにインストールされている場合、そのクライアントが会議を開き、参加します。</span><span class="sxs-lookup"><span data-stu-id="f020a-105">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="f020a-106">クライアントがインストールされていない場合、既定では、2013バージョンの Lync Web App が開きます。</span><span class="sxs-lookup"><span data-stu-id="f020a-106">If a client is not installed, by default the 2013 version of Lync Web App opens.</span></span>

<span data-ttu-id="f020a-107">ユーザーが Office Communicator 2007 R2 または Lync 2010 アテンダントを使用して会議に参加できるようにする場合は、会議参加ページの動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f020a-107">You can modify the behavior of the meeting join page if you want to allow users to join meetings with Office Communicator 2007 R2 or Lync 2010 Attendant.</span></span> <span data-ttu-id="f020a-108">これらの構成オプションは Lync Server 2013 コントロールパネルから削除されましたが、Set-cswebserviceconfiguration コマンドレットを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="f020a-108">These configuration options have been removed from the Lync Server 2013 Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>

### <a name="meeting-join-page-cswebserviceconfiguration-parameters"></a><span data-ttu-id="f020a-109">会議参加ページの CsWebServiceConfiguration のパラメーター</span><span class="sxs-lookup"><span data-stu-id="f020a-109">Meeting Join Page CsWebServiceConfiguration Parameters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f020a-110">CsWebServiceConfiguration のパラメーター</span><span class="sxs-lookup"><span data-stu-id="f020a-110">CsWebServiceConfiguration Parameter</span></span></th>
<th><span data-ttu-id="f020a-111">説明</span><span class="sxs-lookup"><span data-stu-id="f020a-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f020a-112">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="f020a-112">ShowJoinUsingLegacyClientLink</span></span></p></td>
<td><p><span data-ttu-id="f020a-113">True に設定すると、Lync 以外のクライアントアプリケーションを使用して会議に参加しているユーザーには、Office Communicator 2007 R2 を使用して会議に参加する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="f020a-113">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting by using Office Communicator 2007 R2.</span></span> <span data-ttu-id="f020a-114">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="f020a-114">The default value is False.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f020a-115">Showalternatejoinoptionsexpan</span><span class="sxs-lookup"><span data-stu-id="f020a-115">ShowAlternateJoinOptionsExpanded</span></span></p></td>
<td><p><span data-ttu-id="f020a-p104">True に設定した場合、オンライン会議に参加するための別のオプション (Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。False (既定値) に設定されている場合、これらのオプションは使用可能ですが、ユーザーが自分でオプションの一覧を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f020a-p104">When set to True then alternate options for joining an online conference (such as Office Communicator 2007 R2) will automatically be expanded and shown to users. When set to False (the default value) these options will be available, but the user will have to display the list of options for themselves.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-the-meeting-join-page-by-using-lync-server-2013-management-shell"></a><span data-ttu-id="f020a-118">Lync Server 2013 管理シェルを使用して会議参加ページを構成するには</span><span class="sxs-lookup"><span data-stu-id="f020a-118">To configure the meeting join page by using Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="f020a-119">Lync Server 2013 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f020a-119">Start the Lync Server 2013 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f020a-120">次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f020a-120">Run the following cmdlet:</span></span>
    
        Get-CsWebServiceConfiguration
    
    <span data-ttu-id="f020a-121">このコマンドレットは、Web サービス構成設定を返します。</span><span class="sxs-lookup"><span data-stu-id="f020a-121">This cmdlet returns the web service configuration settings.</span></span>

3.  <span data-ttu-id="f020a-122">ユーザーの設定に応じて、パラメーターを True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、「Lync Server 2013 Management Shell」のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f020a-122">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the Lync Server 2013 Management Shell documentation):</span></span>
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

</div>

</div>

<span> </span>

</div>

</div>

</div>

