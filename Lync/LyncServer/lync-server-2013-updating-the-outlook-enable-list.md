---
title: 'Lync Server 2013: Outlook enable list の更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376c5788d535cd893b2261dcddcb1fe05d676005
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Lync Server 2013 の Outlook enable list の更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-07_

Microsoft Lync 2013 用のオンラインミーティングアドインは、Outlook のアドイン管理リストに含まれるポリシーを作成することによって、常にユーザーが有効な状態を保つことができます。 アドイン管理リスト ポリシーは、グループ ポリシー管理コンソールの Office 管理テンプレート ファイルに含まれています。 [HKCU\\\\Software Policies\\Microsoft\\Office\\15.0\\Outlook15\\弾力性\\AddinList] の下にレジストリキーを作成します。 このキーに ucaddin の値を追加し、その値を常に有効にして、ユーザーが手動で無効にできないように ucaddin を構成することができます。

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Outlook アドインの一覧に ucaddin を追加するには

  - AddinList レジストリキーに、[HKCU\\Software\\Policies\\Microsoft\\Office\\15.0\\Outlook15\\弾力性\\AddinList] の下にある次の値を追加します。
    
      - レジストリの種類 =\_REG SZ
    
      - 名前 = ucaddin.dll
    
      - 値 = 1 (アドインが常に有効になりエンド ユーザーが管理できないことを指定します)

</div>

</div>

<span> </span>

</div>

</div>

</div>

