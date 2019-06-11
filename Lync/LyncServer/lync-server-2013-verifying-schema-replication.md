---
title: 'Lync Server 2013: スキーマのレプリケーションの確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="03b55-102">Lync Server 2013 での Active Directory スキーマのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="03b55-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03b55-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="03b55-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="03b55-104">フォレストの準備を実行する前に、スキーマパーティションがレプリケートされていることを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="03b55-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="03b55-105">スキーマレプリケーションを手動で確認するには</span><span class="sxs-lookup"><span data-stu-id="03b55-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="03b55-106">Enterprise Admins グループのメンバーとしてドメインコントローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="03b55-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="03b55-107">[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **adsi の編集**] をクリックして、adsi の編集を開きます。</span><span class="sxs-lookup"><span data-stu-id="03b55-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="03b55-108">または、コマンドラインから<STRONG>adsiedit</STRONG>を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="03b55-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="03b55-109">Microsoft 管理コンソール (MMC) ツリーでまだ選択されていない場合は、[ **ADSI edit**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03b55-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="03b55-110">[**アクション**] メニューで、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03b55-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="03b55-111">[**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03b55-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="03b55-112">スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。</span><span class="sxs-lookup"><span data-stu-id="03b55-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="03b55-113">このオブジェクトが存在し、 **Rangeupper**属性の値が1150であり、 **rangeupper**属性の値が3の場合は、スキーマが正常に更新され、複製されています。</span><span class="sxs-lookup"><span data-stu-id="03b55-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="03b55-114">このオブジェクトが存在しない場合、または**Rangeupper**属性と**rangeupper**属性の値が指定されていない場合は、スキーマが変更されなかったか、レプリケートされませんでした。</span><span class="sxs-lookup"><span data-stu-id="03b55-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03b55-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="03b55-115">See Also</span></span>


[<span data-ttu-id="03b55-116">Lync Server 2013 での Active Directory スキーマの準備の実行</span><span class="sxs-lookup"><span data-stu-id="03b55-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="03b55-117">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="03b55-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

