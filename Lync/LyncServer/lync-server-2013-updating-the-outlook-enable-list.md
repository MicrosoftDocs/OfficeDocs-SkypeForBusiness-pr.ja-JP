---
title: 'Lync Server 2013: Outlook の有効化リストを更新する'
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
ms.openlocfilehash: f44de6e3b7756935829b008c585474e08f6f9969
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Lync Server 2013 の Outlook 有効化リストを更新する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-07_

Microsoft Lync 2013 用のオンライン会議アドインは、Outlook のアドイン管理リストに含めるポリシーを作成することによって、ユーザーが常に有効にしていることを確認できます。 アドイン管理リストポリシーは、グループポリシー管理コンソールの Office 管理用テンプレートファイルに含まれています。 [HKCU\\\\Software ポリシー\\] の下に、レジストリ\\キー\\が\\作成\\さ\\れます。 Microsoft Office 15.0 Outlook15 弾力性 AddinList。 このキーに ucaddin dll の値を追加して、常に有効にし、ユーザーが手動で無効にできないように ucaddin の値を構成することができます。

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Outlook アドインの一覧に ucaddin dll を追加するには

  - AddinList レジストリキーに、[HKCU\\Software\\ポリシー\\Microsoft\\Office\\15.0\\Outlook15\\弾力性\\AddinList] にある次の値を追加します。
    
      - レジストリの種類 =\_REG SZ
    
      - Name = ucaddin .dll
    
      - 値 = 1 (アドインを常に有効にし、エンドユーザーが管理できないことを指定します)

</div>

</div>

<span> </span>

</div>

</div>

</div>

