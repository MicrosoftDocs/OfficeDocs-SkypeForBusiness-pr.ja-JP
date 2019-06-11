---
title: 'Lync Server 2013: お知らせを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb942c57394e2141ad4c550ecaf33ae2ef128fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="63931-102">Lync Server 2013 でお知らせを削除する</span><span class="sxs-lookup"><span data-stu-id="63931-102">Delete an announcement in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63931-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="63931-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="63931-104">次の手順を使用して、割り当てられていない番号への通話に使用されるお知らせを削除します。</span><span class="sxs-lookup"><span data-stu-id="63931-104">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="63931-105">アナウンスを削除するには</span><span class="sxs-lookup"><span data-stu-id="63931-105">To delete an announcement</span></span>

1.  <span data-ttu-id="63931-106">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="63931-106">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="63931-107">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="63931-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="63931-p101">組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63931-p101">List all the announcements in your organization. At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="63931-p102">表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="63931-p102">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="63931-112">例:</span><span class="sxs-lookup"><span data-stu-id="63931-112">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63931-113">その他のオプションの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">csannouncement</A>と Csannouncement の<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">削除</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63931-113">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="63931-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="63931-114">See Also</span></span>


[<span data-ttu-id="63931-115">Lync Server 2013 でお知らせを作成する</span><span class="sxs-lookup"><span data-stu-id="63931-115">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="63931-116">CsAnnouncement の削除</span><span class="sxs-lookup"><span data-stu-id="63931-116">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="63931-117">CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="63931-117">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

