---
title: 'Lync Server 2013: スキーマレプリケーションの確認'
description: 'Lync Server 2013: スキーマレプリケーションの検証。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560173"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="ec437-103">Lync Server 2013 での Active Directory スキーマのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="ec437-103">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec437-104">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ec437-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ec437-105">フォレストの準備を実行する前に、スキーマパーティションがレプリケートされたことを手動で確認してください。</span><span class="sxs-lookup"><span data-stu-id="ec437-105">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="ec437-106">スキーマのレプリケーションを手動で確認するには</span><span class="sxs-lookup"><span data-stu-id="ec437-106">To manually verify schema replication</span></span>

1.  <span data-ttu-id="ec437-107">Enterprise Admins グループのメンバーとしてドメイン コントローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ec437-107">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="ec437-108">**[スタート]** をクリックして **[管理ツール]** をクリックし、**[ADSI エディター]** をクリックして ADSI エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec437-108">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ec437-109">または、コマンド ラインから <STRONG>adsiedit.msc</STRONG> を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ec437-109">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="ec437-110">Microsoft 管理コンソール (MMC) ツリーで、まだ選択されていない場合には **[ADSI エディター]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec437-110">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="ec437-111">**[アクション]** メニューで、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec437-111">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="ec437-112">**[接続の設定]** ダイアログ ボックスの **[既知の名前付けコンテキストを選択する]** で、**[スキーマ]** を選択して **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec437-112">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ec437-113">スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。</span><span class="sxs-lookup"><span data-stu-id="ec437-113">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="ec437-114">このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。</span><span class="sxs-lookup"><span data-stu-id="ec437-114">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="ec437-115">このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。</span><span class="sxs-lookup"><span data-stu-id="ec437-115">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec437-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec437-116">See Also</span></span>


[<span data-ttu-id="ec437-117">Lync Server 2013 での Active Directory スキーマの準備の実行</span><span class="sxs-lookup"><span data-stu-id="ec437-117">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="ec437-118">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="ec437-118">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

