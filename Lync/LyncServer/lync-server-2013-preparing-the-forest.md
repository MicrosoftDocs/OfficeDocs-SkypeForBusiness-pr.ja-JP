---
title: 'Lync Server 2013: フォレストの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35438969d8876875bef3d22b2d0ab676c146189
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506864"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="08810-102">Lync Server 2013 のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="08810-102">Preparing the forest for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08810-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="08810-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="08810-104">「フォレストの準備」では、Lync Server 2013 で使用するために Active Directory のグローバル設定とオブジェクトおよび Active Directory ユニバーサルグループを作成し、Active directory オブジェクトに対する適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="08810-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="08810-105">ユニバーサルグループ、およびフォレストの準備によって作成されるグローバル設定とオブジェクトの説明については、「 [Lync Server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08810-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="08810-106">また、フォレストの準備では、Lync Server 2013 で使用されるプロパティセットと表示指定子を含むオブジェクトを作成し、それらを構成コンテナーに格納します。</span><span class="sxs-lookup"><span data-stu-id="08810-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="08810-107">フォレストの準備手順を実行する前に、スキーマの準備の変更がすべてのドメインコントローラーにレプリケートされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="08810-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="08810-108">レプリケーションが完了していない場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="08810-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="08810-109">新しい Lync Server 展開を実行している場合は、構成コンテナーにグローバル設定を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08810-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="08810-110">以前のバージョンからアップグレードしていて、システムコンテナーにグローバル設定を引き続き格納している場合は、システムコンテナーを引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="08810-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="08810-111">この手順を実行するには、フォレストのルート ドメインの Enterprise Admins グループまたは Domain Admins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="08810-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="08810-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="08810-112">In This Section</span></span>

  - [<span data-ttu-id="08810-113">Lync Server 2013 のフォレストの準備の実行</span><span class="sxs-lookup"><span data-stu-id="08810-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="08810-114">コマンドレットを使用して Lync Server 2013 のフォレストの準備を元に戻す</span><span class="sxs-lookup"><span data-stu-id="08810-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

