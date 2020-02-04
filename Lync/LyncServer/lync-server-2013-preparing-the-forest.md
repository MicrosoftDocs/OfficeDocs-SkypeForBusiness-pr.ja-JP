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
ms.openlocfilehash: 8a485ba2a406fd762d70ba4e8ff621d2d6af3801
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="13054-102">Lync Server 2013 でのフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="13054-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13054-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="13054-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="13054-104">フォレストの準備 Active Directory のグローバル設定とオブジェクト、および Lync Server 2013 で使用する Active Directory ユニバーサルグループを作成し、Active Directory オブジェクトに対する適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="13054-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="13054-105">ユニバーサルグループと、フォレストの準備によって作成されたグローバル設定とオブジェクトの説明については、「 [Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13054-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="13054-106">また、フォレストの準備では、Lync Server 2013 で使用されるプロパティセットと表示指定子が含まれているオブジェクトを作成し、それらを構成コンテナーに保存します。</span><span class="sxs-lookup"><span data-stu-id="13054-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="13054-107">フォレストの準備手順を実行する前に、スキーマ準備の変更がすべてのドメインコントローラーにレプリケートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13054-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="13054-108">複製が完了していない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="13054-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="13054-109">新しい Lync Server 展開を実行する場合は、構成コンテナーにグローバル設定を格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13054-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="13054-110">以前のバージョンからアップグレードする場合でも、システムコンテナーにグローバル設定を保存しておくと、引き続きシステムコンテナーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="13054-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="13054-111">この手順を実行するには、フォレストルートドメインの Enterprise Admins または Domain Admins グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="13054-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13054-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="13054-112">In This Section</span></span>

  - [<span data-ttu-id="13054-113">Lync Server 2013 でのフォレストの準備の実行</span><span class="sxs-lookup"><span data-stu-id="13054-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="13054-114">コマンドレットの使用による Lync Server 2013 のフォレストの準備のリバース</span><span class="sxs-lookup"><span data-stu-id="13054-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

