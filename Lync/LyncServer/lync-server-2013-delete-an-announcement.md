---
title: 'Lync Server 2013: アナウンスの削除'
description: 'Lync Server 2013: アナウンスを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 722028f684734504d86bfc986250a2a1dd17fabc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553673"
---
# <a name="delete-an-announcement-in-lync-server-2013"></a><span data-ttu-id="59b80-103">Lync Server 2013 でのアナウンスの削除</span><span class="sxs-lookup"><span data-stu-id="59b80-103">Delete an announcement in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59b80-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="59b80-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="59b80-105">未使用の番号への通話に使用されるアナウンスを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="59b80-105">Use the following procedure to delete an announcement that is used for calls to unassigned numbers.</span></span>

<div>

## <a name="to-delete-an-announcement"></a><span data-ttu-id="59b80-106">アナウンスを削除するには</span><span class="sxs-lookup"><span data-stu-id="59b80-106">To delete an announcement</span></span>

1.  <span data-ttu-id="59b80-107">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="59b80-107">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="59b80-108">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="59b80-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="59b80-p101">組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="59b80-p101">List all the announcements in your organization. At the command line, run:</span></span>
    
        Get-CsAnnouncement

4.  <span data-ttu-id="59b80-p102">表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="59b80-p102">In the resulting list, locate the announcement you want to delete, and copy the GUID. Then, at the command line, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    <span data-ttu-id="59b80-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="59b80-113">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="59b80-114">その他のオプションの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-help アナウンスメント</A> 」および「 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-csannouncement</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59b80-114">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="59b80-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="59b80-115">See Also</span></span>


[<span data-ttu-id="59b80-116">Lync Server 2013 でアナウンスを作成する</span><span class="sxs-lookup"><span data-stu-id="59b80-116">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)  


[<span data-ttu-id="59b80-117">削除-CsAnnouncement</span><span class="sxs-lookup"><span data-stu-id="59b80-117">Remove-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[<span data-ttu-id="59b80-118">-CsAnnouncement を入手する</span><span class="sxs-lookup"><span data-stu-id="59b80-118">Get-CsAnnouncement</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

