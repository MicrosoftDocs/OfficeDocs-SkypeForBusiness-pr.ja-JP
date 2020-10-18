---
title: 'Lync Server 2013: フォレストの準備'
description: 'Lync Server 2013: フォレストの準備。'
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
ms.openlocfilehash: 275d861ebfe7e0350e7baf120b6e6f2bae6a26ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580003"
---
# <a name="preparing-the-forest-for-lync-server-2013"></a>Lync Server 2013 のフォレストの準備

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

「フォレストの準備」では、Lync Server 2013 で使用するために Active Directory のグローバル設定とオブジェクトおよび Active Directory ユニバーサルグループを作成し、Active directory オブジェクトに対する適切なアクセス許可を付与します。 ユニバーサルグループ、およびフォレストの準備によって作成されるグローバル設定とオブジェクトの説明については、「 [Lync Server 2013 でのフォレストの準備による変更点](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。

また、フォレストの準備では、Lync Server 2013 で使用されるプロパティセットと表示指定子を含むオブジェクトを作成し、それらを構成コンテナーに格納します。

<div>


> [!IMPORTANT]  
> フォレストの準備手順を実行する前に、スキーマの準備の変更がすべてのドメインコントローラーにレプリケートされていることを確認してください。 レプリケーションが完了していない場合は、エラーが発生します。



</div>

新しい Lync Server 展開を実行している場合は、構成コンテナーにグローバル設定を格納する必要があります。 以前のバージョンからアップグレードしていて、システムコンテナーにグローバル設定を引き続き格納している場合は、システムコンテナーを引き続き使用できます。

この手順を実行するには、フォレストのルート ドメインの Enterprise Admins グループまたは Domain Admins グループのメンバーである必要があります。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)

  - [コマンドレットを使用して Lync Server 2013 のフォレストの準備を元に戻す](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

