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

# <a name="preparing-the-forest-for-lync-server-2013"></a>Lync Server 2013 でのフォレストの準備

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

フォレストの準備 Active Directory のグローバル設定とオブジェクト、および Lync Server 2013 で使用する Active Directory ユニバーサルグループを作成し、Active Directory オブジェクトに対する適切なアクセス許可を付与します。 ユニバーサルグループと、フォレストの準備によって作成されたグローバル設定とオブジェクトの説明については、「 [Lync Server 2013 でのフォレストの準備による変更](lync-server-2013-changes-made-by-forest-preparation.md)」を参照してください。

また、フォレストの準備では、Lync Server 2013 で使用されるプロパティセットと表示指定子が含まれているオブジェクトを作成し、それらを構成コンテナーに保存します。

<div>


> [!IMPORTANT]  
> フォレストの準備手順を実行する前に、スキーマ準備の変更がすべてのドメインコントローラーにレプリケートされていることを確認します。 複製が完了していない場合、エラーが発生します。



</div>

新しい Lync Server 展開を実行する場合は、構成コンテナーにグローバル設定を格納する必要があります。 以前のバージョンからアップグレードする場合でも、システムコンテナーにグローバル設定を保存しておくと、引き続きシステムコンテナーを使用できます。

この手順を実行するには、フォレストルートドメインの Enterprise Admins または Domain Admins グループのメンバーである必要があります。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのフォレストの準備の実行](lync-server-2013-running-forest-preparation.md)

  - [コマンドレットの使用による Lync Server 2013 のフォレストの準備のリバース](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

